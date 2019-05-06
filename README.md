# aws-codebuild-extras 
Add extra information of your AWS CodeBuild build via environment variables.

## Usage

Add the following command to the `install` or `pre_build` phase of your buildspec:

    curl -fsSL https://raw.githubusercontent.com/easybib/aws-codebuild-extras/master/install >> extras.sh && . ./extras.sh

Or for better readability, break the installation into two steps.
For example in the `install` phase:
```
phases:
  install:
    commands:
      - echo Installing codebuild-extras...
      - curl -fsSL https://raw.githubusercontent.com/easybib/aws-codebuild-extras/master/install >> extras.sh
      - . ./extras.sh
```
|NAME|VALUE
|---|---|
|CI|true|
|CODEBUILD|true|
|CODEBUILD_GIT_AUTHOR|Committer Name|
|CODEBUILD_GIT_AUTHOR_EMAIL|user@example.com|
|CODEBUILD_GIT_BRANCH|branch name|
|CODEBUILD_GIT_COMMIT|commit hash|
|CODEBUILD_GIT_COMMITTED_AT|commit timestamp|
|CODEBUILD_GIT_MESSAGE|commit message|
|CODEBUILD_GIT_TAG|git tag|
|CODEBUILD_PROJECT|project|
|CODEBUILD_PULL_REQUEST|Pull request number|
|GIT_BRANCH|Alias to CODEBUILD_GIT_BRANCH for CodeClimate|
|GIT_COMMIT_SHA|Alias to CODEBUILD_GIT_COMMIT for CodeClimate|
|GIT_COMMITTED_AT|Alias to CODEBUILD_GIT_COMMITTED_AT for CodeClimate|
