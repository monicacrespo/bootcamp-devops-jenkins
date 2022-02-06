###Create a pipeline from GitHub

Browse the classic UI http://localhost:8080

1. New item, pipeline, demo1-3
2. Select pipeline from source control
3. Git - https://github.com/monicacrespo/bootcamp-devops-jenkins
4. Ensure that the source control branch is main
5. Path to Jenkinsfile demo0/Jenkinsfile
6. Build Now
7. Check

```
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (stage-1)
[Pipeline] dir
Running in /var/jenkins_home/workspace/demo1-3/demo0
[Pipeline] {
[Pipeline] echo 
This is build number 3 of 1.3
[Pipeline] sh
+ echo 'Using a multi-line shell step'
Using a multi-line shell step
+ chmod +x test.sh
+ ./test.sh
Inside the script, demo 1.3
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

![Console Output](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/main/demo0/ConsoleOutput.JPG)