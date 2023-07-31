# simple-jenkins-pipeline

## install jenkins
1. Create an IAM role for EC2 instance.
2. Launch new EC2 instance
3. Select Amazon Ubuntu
4. Select instance size (t2.micro/t2.small should be enough)
5. Configure details. Select IAM role created in first step
6. Create Storage
7. Add tags. e.g. Name: jenkins 
8. Configure Security Group
  * Select name for the security group, e.g. jenkins
  * Add rule for SSH: port 22 and port 8080 for browser access
9. Advanced: paste user data from jenkins_inst.sh
10. Review and launch
11. When the instance is up connect with SSH 
12. run `sudo cat /var/lib/jenkins/secrets/initialAdminPassword` to get initial admin password
13. Open Jenkins in browser - `http://<public-ip>:8080` and insert initial admin password 
14. Continue with Jenkins installation wizard
15. set jenkins USERNAME and PASSWORD
16. install jdk8 in jenkins instance using SSH
17. in Manage Jenkins > Tools: Add JDK
    Name: OracleJDK8
    JAVA_HOME: /usr/lib/jvm/java-1.8.0-openjdk-amd64
18. in Manage Jenkins > Tools: Add MAVEN
Name: MAVEN3
Version: 3.9.3
19. Save

## install jenkins plugins
1. Pipeline Utility Steps
2. Pipeline Maven Integration

## Jenkinsfile contains pipeline as code
## In Jenkins :
New Item / Create a job
    Name: simple-pac
    [ ] Freestyle project
    [x] Pipline
