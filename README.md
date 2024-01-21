# Everything_About_Test
-- CI
--   

## Continuous Integration:

It needs a centralized integration point (Github), so every team member can push their works up. 

Build and Test on Every Code change. 

  Multiple environments, OSecs, configurations. 
  
  Build and Test is Scripted, Part of the Project's Source Code. 
  
  Every Commit will either pass or fail CI. If CI breaks, you need to either fix it or remove the commit you made. 
  
Overcome Developer and Feature Isolation

### GitHub Actions for testing:

#### You could run GitHub Actions on the instance or your local machine. 

![image](https://github.com/zkrguan/Everything_About_Test/assets/97544709/f972c007-0a79-46cc-9114-1eded716c914)

#### A typical workflow with the GitHub CI

You are getting a cloud instance running just for testing, and after you will get the report. If you found any job break, then you could just click on the failed task to find out more details. 

Then go back to your code, fix it and push it. 

Keep doing this until the all the broken CI fixed. 

#### GitHub Workflows can be triggered by different events:

When a new commit is pushed. 

On every PR. 

On every new Git Tag

cron schedule ******

#### GitHub Actions Workflows:

Steps are happening in the sequence. It could be a job, a linux command, a service call, or even use premade instructions. 

![image](https://github.com/zkrguan/Everything_About_Test/assets/97544709/a4f6c2b6-6a46-4d26-acc6-4bead66d0ac3)

## YAML 

A typical YAML file looks like this:

![image](https://github.com/zkrguan/Everything_About_Test/assets/97544709/2442c80d-4db8-4a99-904f-40f6881380e8)

### On: 

You need to specify in what kind of case, this work flow will be triggered. 

### Jobs:

The actual job will be running while the On event happening. 

### Steps:

The items in the steps will need you to have sequence. 

### Name:

The name of the work, when it fails, it will show in the jobs.

### Use: 

where you get the code, you could actually get it from the some directory

### Run:

run the script 


Another more complicated job:

![image](https://github.com/zkrguan/Everything_About_Test/assets/97544709/3e101a64-8484-4e33-b83a-641d467e5dd2)

What is this? There is no on. Wait for it. 

### runs-on: specify the OS you would like to run this. 

### with: 

you are calling the uses with the parameter like node-version :'versioncode', 

### cache: 'npm' 

You are saving all the node modules so next time it runs faster. 

### run: |

When you need to run multiple lines of commands, you need pipe. 

## Unit Testing:

What does the Unit mean? 

It could be functions, modules, and classes. 

It should be covering all the coder paths, so it does not 

