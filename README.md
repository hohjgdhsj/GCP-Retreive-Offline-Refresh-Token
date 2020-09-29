# Google Cloud Platform - How to retrieve Refresh-Token
How to retrieve on offline Refresh Token for your application ?
In this article we authorize the application to send an email on behalf of the user.
For other Google API or scopes it's the same procedure.

### Google Cloud Platform (GCP)
First login you on the [Google Cloud Platform Console][df1] with you Google account.

### Create a New Project
Create a project for your application as it :
<p align="center">
  <img src="https://github.com/vhuynen/GCP-Retreive-Offline-Refresh-Token/blob/master/screenshot/Create%20Project.JPG" width="50%">
</p>

### Enable Gmail RESTfull API for your application
Go to menu : `APIs & Services` >> `Library` search Gmail and enable Gmail API
<p align="center">
  <img src="https://github.com/vhuynen/GCP-Retreive-Offline-Refresh-Token/blob/master/screenshot/Enable%20Gmail%20RestFull%20API.JPG" width="50%">
</p>

### Create credentials to access your enabled APIs
Go to menu : `APIs & Services` >> `Credentials`

Then click on the button : `+ CREATE CREDENTIALS` and go to sub-menu `OAuth client ID` 

Click on `CONFIGURE CONSENT SCREEN` button

Choose radio button `External` and then click `CREATE` button

- Step 1, fill all required fields from App Information form :

- Step 2 `SCOPES` 
  - Click on `ADD OR REMOVE SCOPES`
  - Fill gmail term in the filter and choose the scope `.../auth/gmail.send`
  > Keep in mind that we want to send an email on behalf of user.
  > The scope we need to access is : https://www.googleapis.com/auth/gmail.send
  > All scopes for Gmail API are here [Gmail scopes][scopes]
  - Click on the `UPDATE` button
  - Finally, click on the button `SAVE ANS CONTINUE`
<p align="center">
<img src="https://github.com/vhuynen/GCP-Retreive-Offline-Refresh-Token/blob/master/screenshot/Scope%20Gmail%20Send.JPG" width="50%">
</p>

- Step 3 `Optional info` click on the button `SAVE ANS CONTINUE`
- Step 4 `Summary` click on the button `BACK TO DASHBOARD`

At this step, you have activated Gmail API on your Google Cloud Platform, created an application and defined a **consent screen** for that clients authorize your application to use their credentials on behalf of themselves.
Now that your consent screen has been configured for your application, you can resume you settings by going to menu : `APIs & Services` >> `Credentials`

Then click on the button : `+ CREATE CREDENTIALS` and go to sub-menu `OAuth client ID`
On the screen `Create OAuth client ID` fill the choose list `Application type` with the value `Web application`
Click on button `+ ADD URI` on the section `Authorized redirect URIs` and add the value `https://developers.google.com/oauthplayground`

 
 [df1]: <https://console.cloud.google.com/>
 [scopes]: <https://developers.google.com/gmail/api/auth/scopes>
