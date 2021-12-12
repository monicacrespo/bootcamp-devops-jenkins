How to validate a Jenkinsfile?

cat 01/demo1/1.2/Jenkinsfile | curl --user lemoncode -X POST -F "jenkinsfile=<-" http://localhost:8080/pipeline-model-converter/validate

[[https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/master/ValidateJenkinsfile1.JPG|alt=UIValidateJenkinsfile]]

![Terminal Validate Jenkinsfile](https://github.com/monicacrespo/bootcamp-devops-jenkins/blob/master/ValidateJenkinsfile2.JPG)