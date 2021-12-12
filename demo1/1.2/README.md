Requesting user input

Browse the classic UI http://localhost:8080

1. New item, pipeline, copy item, demo1-1.2 from demo1-1.
2. Path to Jenkinsfile demo1/1.2/Jenkinsfile
3. Build Now 
4. Check. Open console from running build
5. Pauses on input stage - OK or abort
6. User inputs TARGET_ENVIRONMENT (default PROD)
```
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] echo
Testing release 0.0.1...
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy)
[Pipeline] input
Input requested
Approved by lemoncode
[Pipeline] withEnv
[Pipeline] {
[Pipeline] echo
Deploying release 0.0.1 to environment PROD
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] echo
Prints success or failure
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

7. User input ABORT. The next steps are not executed
```
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] echo
Testing release 0.0.1...
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy)
[Pipeline] input
Input requested
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] echo
Prints success or failure
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Rejected by lemoncode
Finished: ABORTED
```