# Zomato-Clone-DevSecOps-

This is a DevSecOps Project.

Directories - Jenkins_Sonardocker_trivy and Zomato

1. Lets Start with Jenkins_Sonardocker_trivy 
   It has a main.tf, provider.tf and install_jenkins.sh file.
   
   1.1 provider.tf establishes the version of terraform we are using and we are using our cloud provider as aws.

   1.2 main.tf is used to create following.
   
      1.2.1 A security group named Jenkins-sg which allows follwoing ports 22 ( for ssh ),443 ( for http ),80 ( for https ),8080 ( for jenkins ),9000 ( for Sonarqube).

      1.2.1 A EC2 instance named Jenkins-sonar which will use install_jenkins.sh file as data to install jenkins , docker ( sonarqube as a container) and trivy.

      Jenkins will be used as our main CI/CD Tool , Docker will be used to containerize our sonarqube as well as final application and Trivy is an open source tool from Aquasec which will scan imag for any vulnerabilities.

2. Next to 

