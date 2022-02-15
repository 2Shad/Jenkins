# Jenkins
Jenkins is a free and open source automation server. It helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery.

![Jenkins](Diagrams/Jenkins_CICD.png)


## Setup SSH Keys with GitHub
- `ssh-keygen -t ed25519 -C "{your_email@example.com}"`
- `eval "$(ssh-agent -s)"`
- `ssh-add ~/.ssh/{ssh-key-name}`
- Go on Github settings and select **New SSH key** in the SSH and GPG keys section.
- Give it a name, and paste in the contents of the `.pub` key value pair.
  
![SSH_Key](GIFs/SSH_keys.gif)

## How to create a Jenkins job
- Can set retention rules
- set build criteria (ex: shell script)

![Create_Job](GIFs/Create_Job.gif)

## How to queue a job to an existing job
- Go to the first job, configure, and choose another build project in post-build actions.
- 
![Queue_Job](GIFs/Queue_Job.gif)

## Connecting Jenkins to GitHub project using SSH keys.
- create new keys using `ssh-keygen -t ed25519 -C "{your_email@example.com}"`
- go on github project, settings, and add the public key in there as usual.
- in jenkins for jobs that requires access to this repo you can add the private key in source management, making sure for URL using SSH, add the private key, and change `master` to `main`.

## Job 1
- add the HTTPS url for the GitHub project
- set source control management to Git, put SSH url here and add the key as stated above.
- GitHub hook trigger for GITScm polling for webhook.
- add script for the job in build
- in GitHub project, go in settings, webhooks, and add new webhook. In here as for payload url `http://13.40.2.254:8080/github-webhook/`, json for content type and save.