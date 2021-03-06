# Call center sample app for Node.js using Bandwidth WebRTC

To run this sample, you'll need a Bandwidth phone number, Voice API credentials and WebRTC enabled for your account. Please check with your account manager to ensure you are provisioned for WebRTC.

This sample will need be publicly accessible to the internet in order for Bandwidth API callbacks to work properly. Otherwise you'll need a tool like [ngrok](https://ngrok.com) to provide access from Bandwidth API callbacks to localhost.

**Unless you are running on `localhost`, you will need to use HTTPS**. Most modern browsers require a secure context when accessing cameras and microphones.

Note that this sample currently works best in Chrome!


### Create a Bandwidth Voice API application
Follow the steps in [How to Create a Voice API Application](https://support.bandwidth.com/hc/en-us/articles/360035060934-How-to-Create-a-Voice-API-Application-V2-) to create your Voice API appliation.

In step 7 and 8, make sure they are set to POST.

In step 9, provide the publicly accessible URL of your sample app. You need to add `/callback` to the end of this URL in the Voice Application settings.

You do no need to set a callback user id or password. 

Create the application and make note of your _Application ID_. You will provide this in the settings below.

### Configure your sample app
Copy the default configuration files

```bash
cp .env.default .env
```

Add your Bandwidth account settings to `.env`:

* ACCOUNT\_ID
* USERNAME
* PASSWORD

Add your Voice Application settings to `.env`:

* VOICE\_APP\_ID (the Voice Application ID from above)
* VOICE\_CALLBACK\_URL (the publicly accessible URL you specified as the callback in the Voice Application, **without** `/callback` in the URL)


### Install dependencies and build

```bash
npm install
npm start
```

### Start your call center
Browse to [http://localhost:3000](http://localhost:3000) to accept calls into your call center.

You should now be able to dial into your phone number and speak to the next available agent!