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

```yaml

on:
  pull_request:
    branches:
      - main
      - 'mona/octocat'
      - 'releases/**'
```

or 

```yaml

job3:
  needs: [job1, job2]

```

Just remember, anything valid in JSON expression will be valid in YAML. 

## YAML 

A YAML is just a super set of JSON. JSON is all about key value pairs. 

Each identation is 2 spaces.

If you have an array of elements, you could either use Json expression way or - - - way. 

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



### runs-on: specify the OS you would like to run this. 

### with: 

you are calling the uses with the parameter like node-version :'versioncode', 

### cache: 'npm' 

You are saving all the node modules so next time it runs faster. 

### run: |

When you need to run multiple lines of commands, you need pipe. 

## Unit Testing:

### What does the Unit mean? 

It could be functions, modules, and classes. 

It should be covering all the coder paths. Not just the normal flow but also the exception flow. 

### Rules and highlights

The tests are independent: No dependency between tests. Order of the tests should not matter. 

Each test focuses on one thing: Avoid large tests. Instead, using more specific and smaller tests. (Save resources)

Assert Correctness: Actual results are compared to expected values. Hardcoding expected outcome is allowed. 

Tests are the documentations: Contract about what units of code should do. Specify our intentions. Some projects have no docs, and the tests are used for that purpose. 

Tests should aid implementation: TDD (Test Driven Development) is also a trend now: think through inputs, outputs, edge cases. Parallelization: One person writes tests another the implementation. Aid Refactoring, Maintenance. (Think about the Old days when we were developing consoles, people actually tries put 0 to remove the line items. We never had that logic to handle.)

Keep in mind that NOT EVERYTHING CAN BE TESTED IN THE UNIT TEST WAY. 

Tests are also codes that must be maintained. Every line of code will potentially generate 3-5 lines. 

Tests should cover 80%-100% of the codes. You don't have to cover everything, but you must keep the testing on a level. 

Example of the coverage information. 

![image](https://github.com/zkrguan/Everything_About_Test/assets/97544709/f2e7d0d5-c574-487a-b975-753766f120b5)

### npm ci

this is commonly used for testing. npm ci will only use the packagelock.json file. So it will only install the exact version you installed. 

the combo is commonly used is 

```md

npm install-ci-test

```


## JEST, Supertest:

Will update more with example codes.

