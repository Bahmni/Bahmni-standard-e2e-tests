# Gauge tests for Bahmni Standard V93 E2E tests

[![Bahmni Standard V94 E2E Tests](https://github.com/Bahmni/Bahmni-standard-e2e-tests/actions/workflows/BahmniStandardV94.yml/badge.svg)](https://github.com/Bahmni/Bahmni-standard-e2e-tests/actions/workflows/BahmniStandardV94.yml)

This repo is for End to End tests for Bahmni Standard V93.

# Pre-requisites
* [Node-js](https://nodejs.org/en/)
* [Gauge](https://docs.gauge.org/getting_started/installing-gauge.html?os=macos&language=javascript&ide=vscode)
* Install Taiko `npm install -g taiko`

# QA Test plan
* The details of scenarios covered and planned are given [here](https://bahmni.atlassian.net/wiki/spaces/BAH/pages/2813427741/QA+Automation+Testing)

# Execution
* npm install
* `gauge run specs --env <ENV> -v -p --tags '<TAGS>'`
eg: `gauge run specs --env local -v -p --tags 'hospital & regression'`

> `--env` allows us to choose the environment on which the tests can run. These are the subfolders of the env folder with relevant property files.

> `-v` runs the tests in the verbose mode

> `-p` runs the tests in parallel, the number of streams will be decided by gauge based on system resources. 
If you want to override it then [-n=<Number_of_streams>](https://docs.gauge.org/execution.html?os=macos&language=javascript&ide=vscode#:~:text=data/uat.-,Parallel%20execution%C2%B6,-Specs%20can%20be) can be included.

> `--tags` allows us to choose the tests to run from the test suite. 
    In this command we are running the tests which are tagges as `hospital` and `regression` from the test suite. 
    
> The HTML reports can be found in `./reports/html-report` after the run.

## To run on local
* `gauge run specs --env local -v -p --tags 'hospital | regression'`
> This will run the test on the URL of the vagrant setup `https://localhost/`. 
If you want to change this you can edit the URLs in `bahmni.properties` in the `<test checkout Folder>/env/local` folder.
