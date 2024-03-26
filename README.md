# Zomato-Clone-DevSecOps

This is a DevSecOps Project.

Directories - Jenkins_Sonardocker_trivy and Zomato
Files - jenkinsfile

1. Lets Start with Jenkins_Sonardocker_trivy 
   It has a main.tf, provider.tf and install_jenkins.sh file.
   
   1.1 provider.tf establishes the version of terraform we are using and we are using our cloud provider as aws.

   1.2 main.tf is used to create following.

      1.2.1 A security group named Jenkins-sg which allows follwoing ports 22 ( for ssh ),443 ( for http ),80 ( for https ),8080 ( for jenkins ),9000 ( for Sonarqube).

      1.2.1 A EC2 instance named Jenkins-sonar which will use install_jenkins.sh file as data to install jenkins , docker ( sonarqube as a container) and trivy.

      Jenkins will be used as our main CI/CD Tool , Docker will be used to containerize our sonarqube as well as final application and Trivy is an open source tool from Aquasec which will scan imag for any vulnerabilities.


# Lets Start with this Directory.

Step 1. Install terraform and awscli on your local machine or codespace depends on where you are working.

Step 2. Configure awscli with AWS Access Token and Secret Key.

Step 3. Run ---> terraform init    ( Initialize Terraform directory and installs required dependencies and plugins) 

Step 4. Run ---> terraform plan / terraform apply ( Applies the changes )

Step 5. Copy the public IP of the instance and open in two windows public-ip:8080 for jenkins and public-ip:9000 for sonarqube.

Step 6. Resister and login in both.

Step 7. Go to Jenkins->Manage Jenkins->Plugins->Available Plugins

Step 8. Search for below and install.
         Eclipse,
         SonarQube Scanner,
         NodeJS,
         OWASP and
         Docker (All related plugins)

Step 9. Go to Jenkins->Manage Jenkins->Tools->JDK installations->Add JDK

Step 10. Give Name as jdk17 , select Install automatically->Install from adoptium.net->Version->jdk-17.0.8.1+1

Step 11. Go to Jenkins->Manage Jenkins->Tools->SonarQube Scanner installations->Add SonarQube Scanner 

Step 12. Give Name as sonar-scanner , select Install automatically->Install from Maven Central->Version->Latest

Step 13. Go to Jenkins->Manage Jenkins->Tools->NodeJS installations->Add NodeJS 

Step 14. Give Name as node16 , select Install automatically->Install from nodejs.org->Version->16.2.0

Step 15. Go to Jenkins->Manage Jenkins->Dependency-Check installation (OWASP)->Add Dependency-Check

Step 16. Give Name as DP-check, select Install automatically->Install from github.com->Version->6.5.1

Step 17. Go to Jenkins->Manage Jenkins->Docker installations->Add Docker

Step 18. Give Name as DP-check, select Install automatically->Install from docker.com->Version->latest


Step 19. Go to Sonarqube and create token - Sonarqube->Administration->Security->users->tokens

Step 20. Give Token name , set expiry and copy generated token.

Step 21. Go to Jenkins->Manage Jenkins->Credentials->System->Global->Add Credentials->Secret text

Step 22. Paste Secret , ID as sonar-token and create

Step 23. Go to Sonarqube and create token - Sonarqube->Administration->Configuration->Webhooks->create

Step 24. 





        









# Now the Second Directory Directory.

2. Next to that we have our Zomato dir that is our application code dir.
   It has public , src dir , package files and Dockerfile.

   2.1 public 
   

