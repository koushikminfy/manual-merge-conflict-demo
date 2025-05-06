# 🧩 Merge Conflicts

## ✅ Tasks Completed

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

### 🔥 Conflict 1: Heading Line Conflict

#### 🔹 Cause of Conflict:

Both branches edited the same `<h1>` line in `index.html`:

* `conflict/style-change` changed it to:

  ```html
  <h1>Hello from the Style Branch!</h1>
  ```

* `conflict/content-change` changed it to:

  ```html
  <h1>Hello from the Content Branch!</h1>
  ```

#### 🔹 Git Conflict Markers:

```html
<<<<<<< HEAD
<h1>Hello from the Style Branch!</h1>
=======
<h1>Hello from the Content Branch!</h1>
>>>>>>> conflict/content-change
```

#### 🔧 Resolution:

Manually replaced it with a merged version:

```html
<h1>Hello from both Style and Content branches!</h1>
```

Marked the file as resolved, committed the fix, and completed the merge.

![Capture\_4](https://github.com/user-attachments/assets/dc2f7d24-5526-4140-93df-f9c566b2a34f)

✅ **Conflict 1 resolved successfully.**

---

### 🔥 Conflict 2: Paragraph Text Conflict

#### 🔹 Cause of Conflict:

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

#### 🔹 Git Conflict Markers:

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

#### 🔧 Resolution:

One conflict was automatically resolved by GitHub. For the second conflict:

Manually edited the file to include both changes in a combined form:

```html
<p>This paragraph is restyled and includes new content from both branches.</p>
```

✅ **Conflict 2 resolved successfully.**
