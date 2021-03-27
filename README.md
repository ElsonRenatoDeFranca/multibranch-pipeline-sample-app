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


How to configure Webhook

1- You have to configure your public ip. You can do this by using this command:

2- URL Webhook: http://localhost:8080//multibranch-webhook-trigger/invoke?token=mytoken

3- If you want to try to run Jenkins on localhost, you have to install ngrok: https://ngrok.com/download which expose localhost urls over internet.

4- After installation of the ngrok, run the following command:
  > ngrok http 8080
  
  The following output will be displayed:

   Forwarding                    http://56e4074cc91a.ngrok.io -> http://localhost:8080 
   Forwarding                    https://56e4074cc91a.ngrok.io -> http://localhost:8080

5- Replace "localhost" by the url provided by ngrok. E.g.(http://56e4074cc91a.ngrok.io)

It will become like this:

http://56e4074cc91a.ngrok.io/multibranch-webhook-trigger/invoke?token=mytoken

