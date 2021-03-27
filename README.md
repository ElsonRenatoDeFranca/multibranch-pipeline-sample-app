# multibranch-pipeline-sample-app


Jenkins and Github integration:

NOTE: Assume the jenkins is working in your container;

1- Login to Jenkins and navigate to Manage Jenkins -> Manage Plugins and go to installed tab;
2- Check if the "Multibranch Scan Webhook Trigger" is set;
3- If you click on the link you'll see the page below:
https://plugins.jenkins.io/multibranch-scan-webhook-trigger/

In this page you'll get the required url for webhook: JENKINS_URL/multibranch-webhook-trigger/invoke?token=TOKENHERE

4- Go to the dashboard;

5- Click on "Multibranch-pipeline-sample-app";

6- Click on "configure";

7- In the page that will appear, go to "Scan Multibranch Pipeline Triggers" section:
    7.1 - Check "Scan by webhook";
	7.2 - In the input text called "Trigger token", put your token name:
	    mytoken


Criando webhook

1- You have to configure your public ip. You can do this by using this command:

https://whatismyipaddress.com/

2- URL Webhook: http://localhost:8080//multibranch-webhook-trigger/invoke?token=mytoken

3- Replace "localhost" by the your public IP described in the site.
