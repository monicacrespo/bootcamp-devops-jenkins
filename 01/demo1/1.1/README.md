Browse the Open Blue Ocean UI http://localhost:8080

0. Delete previous demo1-1.1 and demo1-1.2 pipelines
1. New item, pipeline, copy item, demo1-1.1 from demo1-3.
2. Path to Jenkinsfile 01/demo1/1.1/Jenkinsfile 
3. Build Now 
4. Check. Open console from running build
![BuildStage](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/master/01/demo1/1.1/BuildStage.JPG)

![UnitTestStage](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/master/01/demo1/1.1/UnitTestStage.JPG)

```
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ cd ./01/solution
+ npx -c 'echo $npm_package_version'
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] dir
Running in /var/jenkins_home/workspace/demo1-1.1/01/solution
[Pipeline] {
[Pipeline] echo
Building version 1.0.1 with suffix: rc.2
[Pipeline] sh
+ echo 'Building version 1.0.1 with suffix: rc.2'
Building version 1.0.1 with suffix: rc.2
[Pipeline] sh
+ npm install
added 733 packages, and audited 734 packages in 43s

15 vulnerabilities (11 moderate, 4 high)

To address all issues, run:
  npm audit fix

Run `npm audit` for details.
+ npm run build

> code@1.0.1 prebuild
> rimraf app


> code@1.0.1 build
> tsc

[Pipeline] }
[Pipeline] // dir
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Unit Test)
[Pipeline] dir
Running in /var/jenkins_home/workspace/demo1-1.1/01/solution
[Pipeline] {
[Pipeline] sh
+ npm test

> code@1.0.1 pretest
> jest --clearCache

Cleared /tmp/jest_rs

> code@1.0.1 test
> jest -c ./jest.config.js --detectOpenHandles --verbose -i

PASS src/app.spec.ts (6.815 s)
  /api/
    GET verb
      ✓ should return todos (308 ms)
    GET verb with id parameter
      ✓ should returna single todo (26 ms)
    POST verb creates a new todo
      ✓ should create a new todo (53 ms)

Test Suites: 1 passed, 1 total
Tests:       3 passed, 3 total
Snapshots:   0 total
Time:        6.917 s
Ran all test suites.
[Pipeline] }
[Pipeline] // dir
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```
Note that NPX makes possible to execute a local package as if it's global.

Npx will look for the binary in the node_modules/.bin, if it doesn't find the binary, it will go further down in the files until it finds. If in a case it doesn't find, it will install the binary, execute it and soon after will uninstall it.