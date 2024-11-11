# Jenkinstools
Welcome to Jenkinstools. This is a collection of tools and maintainance jobs for Jenkins.
Multibranch is used differently here: each branch is a separate tool that you can use.

## Setup
Just configure a multibranch job on this repo (more detailed hints to be documented).
Then every branch will run a build. First run will usually fail as Jenkins needs to parse the Jenkinsfile and e.g. create build parameters.
After that, the tools are ready to use.

## Configuration
If you want to modify tools to your needs, just fork the repo.
E.g. you might use other label names.
Please do not file PRs for such changes, but only for changes that are generic or parameterizable and useful for everybody.

## Usage
Most of the branches offer a tool that can just be triggered
Each branch has a more detailed readme as well as help text in the job description and parameters.

## Implemented Tools
none yet

## Planned Tools Backlog
Job config search - find any text in job configuration (config.xml)
Log search - find text in all logs
Credential report - see all credentials linked in one place, also those from folders
Rebuild range of failed runs with parameters
Reload config from disk for single jobs or folders
Create disk usage report for Linux nodes
