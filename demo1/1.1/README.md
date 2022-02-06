Multi-stage pipeline 

Browse the classic UI http://localhost:8080

1. New item, pipeline, demo1-1.1
2. Select pipeline from source control
3. Git - https://github.com/monicacrespo/bootcamp-devops-jenkins.git
4. Ensure that the source control branch is main
5. Path to Jenkinsfile demo1/1.1/Jenkinsfile
6. Build Now
7. Check
```
[Pipeline] withEnv
[Pipeline] {
[Pipeline] withEnv
[Pipeline] {
[Pipeline] echo
Building release 0.0.1 with log level INFO...
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] echo
Testing. I can see release 0.0.1, but not log level
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