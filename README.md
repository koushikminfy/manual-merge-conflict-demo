#  Merge Conflicts

##  Tasks Completed

1. Created a new GitHub repository: `manual-merge-conflict-demo`
2. Added a basic `index.html` file containing a simple webpage:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Merge Conflict Demo</title>
</head>
<body>
  <h1>Hello from GitHub Flow!</h1>
  <p>This is the starting version.</p>
</body>
</html>
```

3. Created two branches from `main`:

   * `conflict/style-change`: Changed the `<h1>` text to "Hello from the Style Branch!"
   * `conflict/content-change`: Changed the same `<h1>` text to "Hello from the Content Branch!"
4. Committed changes in both branches, targeting the same line to intentionally trigger a conflict
5. Created pull requests for both branches
6. Merged the first branch (`conflict/style-change`)
7. Attempted to merge the second branch (`conflict/content-change`) and triggered a **manual merge conflict**
8. Manually resolved the conflict using GitHub’s built-in editor
9. Successfully merged both changes into the `main` branch

---

###  Conflict 1: Heading Line Conflict

####  Cause of Conflict:

Both branches edited the same `<h1>` line in `index.html`:

* `conflict/style-change` changed it to:

  ```html
  <h1>Hello from the Style Branch!</h1>
  ```

* `conflict/content-change` changed it to:

  ```html
  <h1>Hello from the Content Branch!</h1>
  ```

####  Git Conflict Markers:

```html
<<<<<<< HEAD
<h1>Hello from the Style Branch!</h1>
=======
<h1>Hello from the Content Branch!</h1>
>>>>>>> conflict/content-change
```

####  Resolution:

Manually replaced it with a merged version:

```html
<h1>Hello from both Style and Content branches!</h1>
```

Marked the file as resolved, committed the fix, and completed the merge.

![Capture\_4](https://github.com/user-attachments/assets/dc2f7d24-5526-4140-93df-f9c566b2a34f)

 **Conflict 1 resolved successfully.**

---

###  Conflict 2: Paragraph Text Conflict

####  Cause of Conflict:

In this conflict, both branches modified the same paragraph (`<p>`) element in the `index.html` file.

Original line:

```html
<p>This is the starting version.</p>
```

* `conflict/style-change` changed it to:

  ```html
  <p>This paragraph is restyled by the style branch.</p>
  ```

* `conflict/content-change` changed it to:

  ```html
  <p>New content added by the content branch.</p>
  ```

####  Git Conflict Markers:

```html
<<<<<<< HEAD
<p>This paragraph is restyled by the style branch.</p>
=======
<p>New content added by the content branch.</p>
>>>>>>> conflict/content-change
```

![Capture\_](https://github.com/user-attachments/assets/26a75c90-d411-44fd-8223-4f0eebaf1c5c)
![Capture\_2](https://github.com/user-attachments/assets/d954384e-0d8d-4220-bc8a-c2489f3272b8)
![Capture\_3](https://github.com/user-attachments/assets/d5bf63a7-cb80-41be-b71d-cbead5503489)

####  Resolution:

One conflict was automatically resolved by GitHub. For the second conflict:

Manually edited the file to include both changes in a combined form:

```html
<p>This paragraph is restyled and includes new content from both branches.</p>
```

**Conflict 2 resolved successfully.**

## Husky: 
## **Objective:**

Learn to improve **code quality and consistency** through **Git hooks** and basic **CI (Continuous Integration)** using **automation tools**.

---

##  **Tasks Explained:**

### 1. **Set up a repository with Husky and lint-staged**

* **What is Husky?**
  Husky lets you run scripts at different stages of the Git lifecycle (e.g., before a commit or push). It's great for enforcing rules automatically.
* **What is lint-staged?**
  Runs linters (like ESLint) only on files that are staged for commit. This saves time and keeps your commits clean.

> You'll install these with npm/yarn in a JavaScript project:

```bash
npm install husky lint-staged --save-dev
```

Then set up Husky hooks:

```bash
npx husky install
```

Add it to your `package.json` scripts:

```json
"scripts": {
  "prepare": "husky install"
}
```

---

### 2. **Configure pre-commit hooks for:**

* **Code linting** using ESLint (or a language-specific linter like Flake8 for Python)
* **Code formatting** using Prettier
* **Commit message validation** using commitlint + Husky

#### Example Husky setup for pre-commit:

```bash
npx husky add .husky/pre-commit "npx lint-staged"
```

#### `lint-staged` config (in `package.json`):

```json
"lint-staged": {
  "*.js": ["eslint --fix", "prettier --write"]
}
```

#### Commit message validation:

* Install:

  ```bash
  npm install --save-dev @commitlint/{config-conventional,cli}
  ```
* Create `commitlint.config.js`:

  ```js
  module.exports = { extends: ['@commitlint/config-conventional'] };
  ```
* Add Husky commit-msg hook:

  ```bash
  npx husky add .husky/commit-msg 'npx commitlint --edit "$1"'
  ```

---

### 3. **Attempt commits that fail:**

* Commit code that violates linter rules
* Commit badly formatted code
* Use a bad commit message like “update”

All of these should be **rejected** by the respective hook.

---

### 4. **Fix the issues and successfully commit**

* Clean up the code (fix ESLint errors, format with Prettier)
* Use a proper commit message like:
  `feat: add login validation`

---

### 5. **GitHub Actions: Simple CI Workflow**

Create `.github/workflows/ci.yml`:

```yaml
name: Lint Check

on: [push, pull_request]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Node
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - run: npm install
      - run: npm run lint
```

---

##  **Deliverables:**

* A **GitHub repo** with all the above set up
* **Screenshots** showing:

  * Commit failures
  * Commit success
* **GitHub Actions run history** (you can show the "Actions" tab)
* A **`README.md`** section explaining:

  * What automation you set up
  * Benefits like: saved time, reduced bugs, standardized code, etc.

---

Here are the **related topics and key concepts** you should understand or explore to fully grasp Assignment 4: **Git Hooks & Automation**:

---

## 🔧 **Core Tools and Concepts**

### 1. **Git Hooks**

* Client-side vs server-side hooks
* Pre-commit, commit-msg, pre-push, etc.
* Custom scripts in `.git/hooks/` (native Git hooks)
* Husky as a modern hook manager

### 2. **Husky**

* How Husky makes managing hooks easier
* How to install and configure hooks with Husky
* Integrating Husky with linting, formatting, and commitlint

### 3. **lint-staged**

* Running linters and formatters on **staged files only**
* Benefits: faster performance, avoids linting the whole project
* Works with any file type (JS, TS, CSS, etc.)

---

##  **Code Quality Tools**

### 4. **ESLint**

* JavaScript/TypeScript linter
* Rules and plugins
* Auto-fixing with `--fix`
* Using `.eslintrc.json` or `.eslintrc.js`

### 5. **Prettier**

* Code formatter (style rules only, not logic)
* Automatically formats code consistently
* Works with many languages (JS, HTML, CSS, etc.)

---

## 🔏 **Commit Standards**

### 6. **commitlint + Conventional Commits**

* Enforces commit message format like:
  `type(scope): subject` (e.g., `feat(auth): add login button`)
* Common types: `feat`, `fix`, `chore`, `docs`, `test`, `refactor`
* Useful for changelogs, semantic versioning, and clarity

---

##  **Automation and CI/CD**

### 7. **GitHub Actions**

* Automating tasks like:

  * Linting
  * Running tests
  * Building apps
* `on: push` and `on: pull_request` triggers
* YAML syntax for workflows
* Understanding `jobs`, `steps`, and using actions like `actions/checkout` and `setup-node`

---

## **Optional Advanced Topics (if curious)**

### 8. **Semantic Release**

* Automates versioning and changelog generation based on commit messages

### 9. **Pre-commit Framework** (non-JS projects)

* Especially for Python: [https://pre-commit.com/](https://pre-commit.com/)

### 10. **Monorepos & Nx / TurboRepo**

* If you're working with multiple projects in one repo, managing linting/hooks gets more complex

---

##  **Practical Skills Gained**

* Automating quality checks before code is pushed
* Reducing bugs from bad commits
* Creating self-validating workflows
* Ensuring team-wide code consistency

---



