Browse the Open Blue Ocean UI http://localhost:8080

1. New item, pipeline, copy item, demo1-1.2 from demo1-1.1.
2. Path to Jenkinsfile 01/demo1/1.2/Jenkinsfile 
3. Build Now 
4. Check. Open console from running build
    
    Build Stage
![BuildStage](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/main/01/demo1/1.1/BuildStage.JPG)

    
    Unit Tests Stage    
![UnitTestStage](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/main/01/demo1/1.1/UnitTestStage.JPG)

    Console Output with RC being false
    ```
    Started by user lemoncode
    Obtained 01/demo1/1.2/Jenkinsfile from git https://github.com/monicacrespo/bootcamp-devops-jenkins.git
    [Pipeline] Start of Pipeline
    [Pipeline] node
    Running on Jenkins in /var/jenkins_home/workspace/demo1-1.2
    [Pipeline] {
    [Pipeline] stage
    [Pipeline] { (Declarative: Checkout SCM)
    [Pipeline] checkout
    Selected Git installation does not exist. Using Default
    The recommended git tool is: NONE
    No credentials specified
    > git rev-parse --resolve-git-dir /var/jenkins_home/workspace/demo1-1.2/.git # timeout=10
    Fetching changes from the remote Git repository
    > git config remote.origin.url https://github.com/monicacrespo/bootcamp-devops-jenkins.git # timeout=10
    Fetching upstream changes from https://github.com/monicacrespo/bootcamp-devops-jenkins.git
    > git --version # timeout=10
    > git --version # 'git version 2.34.1'
    > git fetch --tags --force --progress -- https://github.com/monicacrespo/bootcamp-devops-jenkins.git +refs/heads/*:refs/remotes/origin/* # timeout=10
    > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
    Checking out Revision d77854c3252f7919c05bd251ca1b680c57d36809 (refs/remotes/origin/main)
    > git config core.sparsecheckout # timeout=10
    > git checkout -f d77854c3252f7919c05bd251ca1b680c57d36809 # timeout=10
    Commit message: "Added directory"
    > git rev-list --no-walk d77854c3252f7919c05bd251ca1b680c57d36809 # timeout=10
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
    [Pipeline] sh
    + '[' false '==' false ]
    + echo -n rc.2+ci.2
    [Pipeline] withEnv
    [Pipeline] {
    [Pipeline] dir
    Running in /var/jenkins_home/workspace/demo1-1.2/01/solution
    [Pipeline] {
    [Pipeline] echo
    Building version 1.0.1 with suffix: rc.2
    [Pipeline] sh
    + npm install
    npm WARN old lockfile 
    npm WARN old lockfile The package-lock.json file was created with an old version of npm,
    npm WARN old lockfile so supplemental metadata must be fetched from the registry.
    npm WARN old lockfile 
    npm WARN old lockfile This is a one-time fix-up, please be patient...
    npm WARN old lockfile 

    up to date, audited 732 packages in 10s

    32 packages are looking for funding
      run `npm fund` for details

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
    [Pipeline] // withEnv
    [Pipeline] }
    [Pipeline] // stage
    [Pipeline] stage
    [Pipeline] { (Unit Test)
    [Pipeline] dir
    Running in /var/jenkins_home/workspace/demo1-1.2/01/solution
    [Pipeline] {
    [Pipeline] sh
    + npm test

    > code@1.0.1 pretest
    > jest --clearCache

    Cleared /tmp/jest_rs

    > code@1.0.1 test
    > jest -c ./jest.config.js --detectOpenHandles --verbose -i

    PASS src/app.spec.ts (8.823 s)
      /api/
        GET verb
          ✓ should return todos (443 ms)
        GET verb with id parameter
          ✓ should returna single todo (40 ms)
        POST verb creates a new todo
          ✓ should create a new todo (123 ms)

    Test Suites: 1 passed, 1 total
    Tests:       3 passed, 3 total
    Snapshots:   0 total
    Time:        8.963 s
    Ran all test suites.
    [Pipeline] }
    [Pipeline] // dir
    [Pipeline] }
    [Pipeline] // stage
    [Pipeline] stage
    [Pipeline] { (Publish)
    Stage "Publish" skipped due to when conditional
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

  Publish Stage Output with RC being true
  
  ![Publish](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/main/01/demo1/1.2/publishStage.JPG)

  Artifacts in jenkins      
  ![](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/main/01/demo1/1.2/ArtifactsNonBlueOcean.JPG)
  
  Artifacts tab in blue ocean     
  ![](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/main/01/demo1/1.2/ArtifactsBlueOcean.JPG)

