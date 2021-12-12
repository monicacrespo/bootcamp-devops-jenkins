How to validate a Jenkinsfile?

cat 01/demo1/1.2/Jenkinsfile | curl --user lemoncode -X POST -F "jenkinsfile=<-" http://localhost:8080/pipeline-model-converter/validate


<img src="ValidateJenkinsfile1.JPG">

<img src="ValidateJenkinsfile2.JPG">
