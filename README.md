# Jenkins

## Setup SSH with Github
- `ssh-keygen -t ed25519 -C "{your_email@example.com}"`
- `eval "$(ssh-agent -s)"`
- `ssh-add ~/.ssh/{ssh-key-name}`
- Go on Github settings and select **New SSH key** in the SSH and GPG keys section.
- Give it a name, and paste in the contents of the `.pub` key value pair.
  


## How to create a Jenkins job
![Create_Job](GIFs/Create_Job.gif)

## How to queue a job to an existing job
![Queue_Job](GIFs/Queue_Job.gif)