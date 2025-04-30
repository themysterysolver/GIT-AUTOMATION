# GIT-ACTION
- yml/yaml is a helps in automate taks like testing,building and deploying code 
- We can learn this in (*github actions*)[https://docs.github.com/en/actions]
---
#### CRON
- Time based job sheduler
```
*    *    *    *    *    <command>
-    -    -    -    - 
|    |    |    |    |
|    |    |    |    +---- Day of the week (0 - 7) (Sunday = 0 or 7)
|    |    |    +--------- Month (1 - 12)
|    |    +------------ Day of the month (1 - 31)
|    +------------- Hour (0 - 23)
+-------------- Minute (0 - 59)

```
```
cron: '0 18 * * *'
```
#### TRIGGER DOWN
- commenting the `shedule` part of `on`
---
#### run : |
- `run: |` lets you write clean, readable multi-line scripts in YAML.
---
#### git config user.name and git config user.email
- They help in git configuration for the commit
- `git config user.name "github-actions"`: Sets the Git username to "github-actions". This is the name that will appear in the commit history.
- `git config user.email "github-actions@github.com"`: Sets the Git email address to "github-actions@github.com". This is the email associated with the commit
- **NOTE** Git requires this for everry commit bu thtis is usally handled by your local system.
---
#### CHECKOUT
```
- name: Checkout code
  uses: actions/checkout@v3
```
- This step tells GitHub Actions to "check out" (download) your repository’s code into the runner (a temporary virtual machine that runs your workflow).
- ***uses*** is a keyword that tells the workflow to run a reusable action — basically, a predefined set of steps written by someone else.
---
