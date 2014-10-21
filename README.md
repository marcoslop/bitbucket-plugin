bitbucket-plugin
================

Fork of https://github.com/jenkinsci/bitbucket-plugin

This plugin has been extended so that not all jobs that have the trigger "Build when a change is pushed to BitBucket" are launched when a new hook POST is received from Bitbucket.
The branch configured in the job must match the branch of the commit.

So that this plugin works you only have to follow these steps:

- Check the trigger "Build when a change is pushed to BitBucket" on each job.
- Configure the hook in bitbucket: "JENKINS_URL/bitbucket-hook/". NOTE that it MUST finish in '/'.
- Generate manually the hpi file: 'mvn clean package'. If tests fail, use 'mvn clean package -DskipTests'

If you want that a merge into a branch, also generates a job execution you must execute the merge so that it generates a new commit: git merge --no-ff <branch>
