# Securing CI process

## Task
It is necessary to implement signature verification for commits in Gitlab-ce, as well as to stop the execution of the pipeline on the gitlab-runner side in case the signature does not match.

## Part 1
    1. Install Ubuntu 22.04  and allocate 4 GB of RAM to it. To install GitLab-ce, follow a tutorial or video guide
    2. To install GitLab-ce, follow a tutorial or video guide
•	Need to install curl - sudo apt install curl
•	Don't forget to edit /etc/hosts
    3. Create a gpg key pair
•	Help- https://docs.gitlab.com/ee/user/project/repository/signed_commits/gpg.html
•	Specify email  admin@example.com   
4. Copy the public part of the key to User Settings>GPG Keys.
    5. Clone the previously created project.
    6. Create any file/script and commit the changes, not forgetting to sign it

## Part 2
    1.Install gitlab-runner tutorial (Needed for executing pipelines after pushing commits).
    2. Register the runner, whereby the executor is specified as shell (Register token you can find in Project>Settings>CI/CD>Runners).
    3. In the runner settings, you need to select this option
 
    4. Create the Pipeline. (You need to create a file in the project - .gitlab-ci.yml) 
    5. The contents of this file can be (export will show all the env variables. Hint  - this may help you to realize checking the commit sign)
    6. Implement signature verification on the runner side, via config file /etc/gitlab-runner/config.toml
    7. To make everything work, you need to import the public key of the user who signs on behalf of the  gitlab-runner user
