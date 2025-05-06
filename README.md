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

###    ---> in github  as it is the small change it will get automatically changed by github

HERE ARE SOME OF THE SCREENSHOTS OF 1ST CONFLICT






![Capture_](https://github.com/user-attachments/assets/26dabc5d-82e7-4c32-bea5-9a03739b2d47)
![Capture_2](https://github.com/user-attachments/assets/8a4fae47-174f-4640-989e-64ee8f2c6ba2)
![Capture_3](https://github.com/user-attachments/assets/814ae6bf-b9e5-4e63-81f6-40256384e38c)


### 🔥 Conflict 2: Paragraph Text Conflict

#### 🔹 Cause of Conflict:
In this conflict, both branches modified the same paragraph (`<p>`) element in the `index.html` file.

Original line:
```html
<p>This is the starting version.</p>
![Capture_4](https://github.com/user-attachments/assets/db8bf5ee-5259-4c62-8141-4bf9d5f27bc1)
