# GIT-ACTION
---
### INTRO TO GITHUB ACTIONS

#### GitHub Automation Workflows

- This repository contains `GitHub Actions workflows` to automate commit to maintain a daily streak
- ***GitHub Actions*** is a powerful automation tool built into GitHub that allows you to automate *workflows* for your repository. 
- Workflows are defined using `YAML files` and can automate tasks like continuous integration (CI), continuous deployment (CD), testing, linting, and more.
---
#### Key Concepts of GitHub Actions:
- `Workflow`: A set of automated steps defined in a YAML file. Workflows are triggered by events like pushes, pull requests, or on a schedule.
- `Action`: A reusable unit of code that performs a specific task within a workflow. GitHub provides many pre-built actions, or you can create your own.

- `Job`: A collection of steps that run on the same runner (environment). Jobs can run sequentially or in parallel.

- `Step`: A single task that can run commands or use actions in a job.

- `Runner`: A server that runs the workflows. GitHub provides hosted runners, or you can use self-hosted runners.

- `Event`: An occurrence that triggers a workflow, like a push, pull_request, schedule, etc.
---
#### Workflows

1. **blank.yml**: trigger using push and pull

2. **commit-keeper.yml**:`main puprpose` creates a commit on 11:30PM if there is no commit till that point of time

3. **hello.yml**:creates a textfile hello on each day at 10:25PM
---

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
- Required so git commit doesn't fail with identity error.
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
### date -u UTC to IST
```
#cron format
minute hour day month day_of_week

```
- IST = UTC + 5:30
- `UTC`- Coordinated universal time
- `IST` - Indian Standard Time
```
# To convert 10:10 PM IST → UTC, subtract 5 hours and 30 minutes
10:10 PM IST - 5 hours 30 minutes = 4:40 PM UTC
```
- prints current date and time
```
Tue Apr 30 14:35:42 UTC 2025

```
- `-u` UTC
- gets the date in `YYYY-MM-DD` format.
```
$(date -u +"%Y-%m-%d")
2025-04-30
```
- `--pretty=oneline` this makes the commit to show line per commit
- `wc -l`  **wc** word count **-l** no of lines 
- **$GITHUB_ENV** stores varaibe so that it cna be used in next step.
- `fromJson(env.commit_count)` safely converts the string env var to a number
---
### Permissions
- You enabled "Workflow permissions: Read and write"
- (in Settings > Actions > General > Workflow permissions).
---
### workflow_dispatch:
- helps u manually run the flow
- manuall trigger button to run the workflow
---
### on:
- it defines when the schedule to run
---
### mkdir -p
- creates an parent
---
