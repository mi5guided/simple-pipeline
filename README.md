# simple-pipeline (Pipeline script from SCM)
Creating a simple Jenkins pipeline

Notes below are from: <br>
https://jenkins.io/pipeline/getting-started-pipelines/<br>
https://plugins.jenkins.io/github<br>

## Approaches to Defining Pipeline Script
You can create pipelines in either of the following ways:
  - Through script entered in the configuration page of the user interface for your Jenkins instance.
  - Through script that you create with a Groovy editor outside Jenkins but import into a designated Jenkins repository by selecting the Pipeline Script from SCM option during initial setup.

## Basic Groovy Syntax for Pipeline Configuration
You typically add functionality to a new pipeline by performing the following tasks:
  - Adding nodes
  - Adding more complex logic (usually expressed as stages and steps)
  - Using the “ws” step to create additional workspace on an agent without taking another executor slot

To configure a pipeline you have created through the Jenkins UI, select the pipeline and click Configure.

If you run Jenkins on Linux or another Unix-like operating system with a Git repository that you want to test.
For example, you can do that with syntax like the following, substituting your own name for “joe-user”:

```
node {
    git url: 'https://github.com/joe_user/simple-maven-project-with-tests.git'
    def mvnHome = tool 'M3'
    sh "${mvnHome}/bin/mvn -B verify"
}
```

## Advanced Groovy Syntax for Pipeline Configuration
Groovy lets you omit parentheses around function arguments. The named-parameter syntax is also a shorthand for creating a map, which in Groovy uses the syntax [key1: value1, key2: value2], so you could write:

```
git([url: 'https://github.com/joe_user/simple-maven-project-with-tests.git', branch: 'master'])
```
For convenience, when calling steps taking only one parameter (or only one mandatory parameter) you can omit the parameter name. For example:
```
sh 'echo hello'
```
is really shorthand for:
```
sh([script: 'echo hello'])
```
