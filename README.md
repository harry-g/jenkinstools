# Jenkinstools
Welcome to Jenkinstools. This is a collection of tools and maintainance jobs for Jenkins development, operation and administration. 

🚧 This is still work in progress - you can watch the progress below in the implemented/backlog section and you are welcome to help. 

The idea of this project is to help Jenkins admins and pipeline developers in daily life. Unlike many plugins focused on job level results, we are more focused on Jenkins housekeeping on job, controller and agent level - and without developing tons of new plugins as we already have too many. Many tasks can just be done in a build job instead of a plugin. This are the ideas where this project starts from.

Multibranch is used differently here: each branch is a separate tool that you can use. This way you just reference this repo and you have all tools handy as single tool jobs in "branches".

⚠️ These tools are very powerful and can **delete jobs or mess up Jenkins or job configuratiosn completely**! Compare it to Jenkins script console. **By using this project you agree to use it at your own risk** and you should **only give Jenkins admins access** to these tool jobs. 

## Setup
Just configure a multibranch job on this repo (more detailed hints to be documented). Then every branch will run a build. First run will usually fail as Jenkins needs to parse the Jenkinsfile and e.g. create build parameters. 

The project runs without changes if at least one Linux and Windows agent is labeled with "OS:Linux" and "OS:Windows" and if safe html is enabled as markup formatter. Otherwise see section configuration below.

Furthermore, many scripts will need many script approvals (page "in-process script approvals"). There are several ways to handle this. See https://plugins.jenkins.io/script-security as a starting point and https://plugins.jenkins.io/permissive-script-security/ as a possible, but less secure solution.

After that, the tools are ready to use and some will run nightly (all fast and with low resource consumption).

## Configuration
If you want to modify tools to your needs like different labels or cron schedules, just fork the repo. Please _do not file PRs for such changes_, but only for changes that are generic or parameterizable and useful for everybody.

It is planned to add also config possibilities outside the source code like global env variables or a global config file.

## Usage
Each branch offers a tool that can just be triggered as build run with according parameters.

Each branch has a more detailed readme as well as help text in the job description and in the parameters.

## Implemented Tools
* none yet

## Planned Tools Backlog
* Job config search - find any text in job configuration (config.xml) of a job/all jobs in a folder
* Pipeline code search - find any text for all jobs in a folder in last used pipeline scripts (no matter if in Jenkinsfile or UI)
* Log search - find text in all build logs of a job/folder
* Rebuild range of (e.g. failed) build runs (with original parameters if any)
* Reload config from disk for single jobs or folders
* Create disk usage report for Linux nodes
* Clean workspace of all/selected agents
* Clean orphan workspaces on all agents
* Clean Gradle cache of all/selected agents
* Delete job(s) by folder and regex
* Delete old build runs without starting a build (Trigger log rotation)
* Report credentials - see all credentials in one place with link, also those from folders
* Report all jobs with custom workspaces
* Report all jobs with certain status (disabled, failing etc.)
* Report existing build runs (e.g. over certain number, kept forever and/or without description)
* Report all label usage in jobs
* Report pipeline libraries and their usage
* Report tool usage (like JDK or Maven etc. sorted by versions)
* Report all SCM trigger configurations (e.g. cron expression)
