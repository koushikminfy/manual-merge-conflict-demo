# manual-merge-conflict-demo
## ✅ Tasks Completed

1. Created a new GitHub repository: `manual-merge-conflict-demo`
2. Added a basic `index.html` file containing a simple webpage
3. Created two branches from `main`:
   - `conflict/style-change`: Changed the `<h1>` text to "Hello from the Style Branch!"
   - `conflict/content-change`: Changed the same `<h1>` text to "Hello from the Content Branch!"
4. Committed changes in both branches, targeting the same line to intentionally trigger a conflict
5. Created pull requests for both branches
6. Merged the first branch (`conflict/style-change`)
7. Attempted to merge the second branch (`conflict/content-change`) and triggered a **manual merge conflict**
8. Manually resolved the conflict using GitHub’s built-in editor
9. Successfully merged both changes into the `main` branch


## ⚠️ Merge Conflict Explanation

A merge conflict happened because both branches modified the **same line** in `index.html`:
### Conflict 1: Paragraph Text Conflict
```html
<h1>Hello from GitHub Flow!</h1>

<<<<<<< HEAD
<h1>Hello from the Style Branch!</h1>
=======
<h1>Hello from the Content Branch!</h1>
>>>>>>> conflict/content-change

 ---> in github  as it is the small change it will get automatically changed by github
