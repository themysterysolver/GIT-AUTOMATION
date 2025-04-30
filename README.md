### 🚀Github-automation 
---
This repository automates commits to GitHub to ensure you don't lose your daily commit streak, even if you forget to make a commit manually. By using **GitHub Actions**, this setup triggers actions based on specific conditions, helping you automate the commit process and maintain your streak.🕺✨

---

### why this repo? 🤔
- To automate commit when there is no commit made till EOD.
- I don't wanna loose a daily streak tbh.
- I wanted to automate this for a long time in git.
- I wanted to to learn *github actions*
---
### How to use it? ⚙️
-  `Fork` the repo
- Then change the *permission*  🍴
    - (in ⚙️Settings > Actions > General > Workflow permissions) 
    - You enabled "Workflow permissions: Read and write"
    
---
### Repo structure🗂️ 
```
.
├── README.md
├── hello_world.txt
├── the_making.md
└── .github
    └── workflows
        ├── blank.yml
        ├── commit-keeper.yml
        └── hello.yml
```
- `the_making.md` contains a brief intro on **github actions**
- `blank.yml` is used to trigger event for each push and pull,got from default template
- `hello.yml` creates a text file at each day on 10:25PM
- `commit-keeper.yml` is used to create a file when there is no commit made till EOD.
---