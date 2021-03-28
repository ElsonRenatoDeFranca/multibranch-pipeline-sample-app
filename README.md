# multibranch-pipeline-sample-app - CI/CD using Jenkins and Github

This project aims to provide an overview about the integration between a simple pipeline built on top on Jenkins and a code on Github. 

### Preconditions

1- Firstly you need to install Docker as container manager in your local environment. Since everything will run on a container.
2- After that, you'll need to instal Jenkins on your Docker. You can do this file by typing the following command line below:

``docker pull jenkins/jenkins:lts``

2.1 - After the installation is completed, please type the following command below:

``docker images``

2.2 - Then, start your Jenkins instance:

 ``docker run --detach --publish 8080:8080 --volume jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts``

2.3 - Set the admin password for your Jenkins instance:

``docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword``

2.4 - Copy and paste in the Jenkins admin screen, the initial password that was displayed in the prompt;

2.5 - After that, set your admin user credentials;

2.6 - Please wait until all mandatory plugins are installed. Once it is finished you can use the Jenkins.

### Tools used in this project

1- Docker;
2- Jenkins;
3- SpringBoot application;
4- Gradle;
5- Java 8+

The application was created by using Spring Initializr. It has only the basic SpringBoot application structure and the Jenkinsfile.

### Jenkins and Github integration:

In order to enable the Continuous Integration/Continuous Deployment in your container, you need to use the WebHook. It is a mechanism that allows the integration between your repository and the Jenkins instance running on your container. In order to do this, please follow the steps below:


1- Login to Jenkins and navigate to Manage Jenkins -> Manage Plugins and go to installed tab;
2- Check if the "Multibranch Scan Webhook Trigger" is set;
3- If you click on the link you'll see the link: https://plugins.jenkins.io/multibranch-scan-webhook-trigger/

    In this page you'll get the required url for webhook: JENKINS_URL/multibranch-webhook-trigger/invoke?token=TOKENHERE

4- Go to the dashboard;

5- Click on "Multibranch-pipeline-sample-app";

6- Click on "configure";

7- In the page that will appear, go to "Scan Multibranch Pipeline Triggers" section:
    7.1 - Check "Scan by webhook";
    7.2 - In the input text called "Trigger token", put your token name:
	    mytoken


### How to configure Webhook

1- You have to configure your public ip. You can do this by using this command:

2- URL Webhook: http://localhost:8080//multibranch-webhook-trigger/invoke?token=mytoken

3- If you want to try to run Jenkins on localhost, you have to install ngrok: https://ngrok.com/download which expose localhost urls over internet.

4- After installation of the ngrok, run the following command:
  ``ngrok http 8080``
  
  The following output will be displayed:

   ``Forwarding http://56e4074cc91a.ngrok.io -> http://localhost:8080`` 
   ``Forwarding https://56e4074cc91a.ngrok.io -> http://localhost:8080``

5- Replace ``localhost`` by the url provided by ngrok. ``e.g.(http://56e4074cc91a.ngrok.io)``

It will become like this:

http://56e4074cc91a.ngrok.io/multibranch-webhook-trigger/invoke?token=mytoken

NOTE: Every time you restart your local machine, you'll need to expose your public ip to Github again.

