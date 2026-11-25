# SCM Lecture 03 Lab: Jenkins Pipeline for a Java Application

## Assignment scope

The supplied lab asks for a Java `HelloWorld` program, a Jenkinsfile with Compile and Run stages, a Jenkins Pipeline job that reads the Jenkinsfile from GitHub, a GitHub push webhook, and a successful triggered build.

## Project files

- `HelloWorld.java`: required sample Java program.
- `Jenkinsfile`: declarative pipeline with Compile and Run stages. It uses the lab's `sh` commands on Unix agents and equivalent `bat` commands on Windows agents.

## Local verification

The Java source was compiled and run locally. Expected output:

```text
Hello, World!
```

## Jenkins and GitHub configuration

1. Push these two files to the root of a GitHub repository.
2. In Jenkins, create a Pipeline job named `HelloWorldPipeline`.
3. Under Pipeline, select **Pipeline script from SCM**, choose **Git**, and enter the repository URL and branch. Set Script Path to `Jenkinsfile`.
4. Save, then choose **Build Now**. Confirm that the Compile and Run stages pass and the Run console output contains `Hello, World!`.
5. In GitHub repository **Settings > Webhooks**, add `http://<reachable-jenkins-host>/github-webhook/`, select **Just the push event**, and save. Jenkins must be reachable from GitHub; `localhost` is not reachable by GitHub's servers.
6. Enable the GitHub hook trigger for GITScm polling in the Jenkins job's build triggers (or use the corresponding GitHub integration trigger available in the installed Jenkins version).
7. Push a small change and verify that GitHub delivers the event and Jenkins starts a new successful build.

## Completion record

The Java compile-and-run portion is prepared for local use. A Jenkins controller and GitHub repository were not available in this environment, so no Jenkins build or live webhook delivery is claimed. Complete the connection-dependent steps above with the course repository and Jenkins host, then add screenshots of the successful Jenkins stages and GitHub webhook delivery if the instructor requires evidence.
