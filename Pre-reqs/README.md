# Running Jenkins in docker
The start_jenkins.sh script and Dockerfile are the ones detailed in [Lemoncode](https://github.com/Lemoncode/bootcamp-devops-lemoncode/tree/master/03-cd/01-jenkins/00-instalando-jenkins).

Steps in the following order using Git Bash if your system is Windows 64:
1. Ensure that script have permissions to be executed: `chmod +x start_jenkins.sh`
2. Build image from Dockerfile: `docker build -t lemoncode/jenkins .`
3. Run Jenkins in Docker. From previous image we can run custom Jenkins version as follows:
    `./start_jenkins.sh lemoncode/jenkins jenkins jenkins-docker-certs jenkins-data`
    
    ```
    7f1f92392f6464fe71580157c6a72b33af580600759d680a1a66199c21e95702
    69727b55ddfd6c8eb416736e989692470ebe101480412eff02cd0f566767f2f1
    ```
    
    After this command finishes, run docker ps  to see a list of containers installed.

    | CONTAINER ID  | IMAGE             | COMMAND           | CREATED   | STATUS    |PORTS |NAMES |
    | --------------| ------------------|-------------------|-----------|-----------|------|------|
    | 69727b55ddfd  | lemoncode/jenkins|"/sbin/tini -- /usr/…"|18 minutes ago|Up 18 minutes|0.0.0.0:8080->8080/tcp, 0.0.0.0:50000->50000/tcp|jenkins-blueocean|
    | 7f1f92392f64  | docker:dind    |"docker-entrypoint.…"|18 minutes ago|Up 18 minutes|2375-2376/tcp|jenkins-docker|

4. Proceed to the [Post-installation setup wizard](https://www.jenkins.io/doc/book/installing/docker/#setup-wizard)

    1. At this moment we have docker container of a Jenkins image running on the port 8080. If we visit localhost:8080 in the browser, we will see the web portal of Jenkins that will ask for the admin password to unlock Jenkins.
    Because I am running Jenkins inside docker as a detached container, to print the password in the console I can use:
    ```
    docker exec -it -u root jenkins-blueocean bash
    bash-5.1# cat /var/jenkins_home/secrets/initialAdminPassword    
    ``` 
    
    2. Now install the suggested plugins and wait until Jenkins finishes. After finishing the installation process Jenkins can be used to create new pipelines and fully usable.
