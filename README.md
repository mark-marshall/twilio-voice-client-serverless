# Severless Functions to support Twilio Voice Client

## Background
This is an implementation of a backend service that can be used to support a Twilio Voice Client application. It is comprised of 3 endpoints:

1) A /token endpoint which expects to receive an identity parameter in the request and returns a Twilio token with a Voice Grant.
2) A /make call endpoint which acts as a TwiML App that is hit whenver the client makes an outbound call. It connects the call with a recpient.
3) A /receive call endpoint which the inbound Twilio number is pointed to and connects the caller with the client.

## Set-up
Before running anything loally, make sure that you have done the following:

1) Create a new API Key in the Twilio Console [here](https://console.twilio.com/us1/account/keys-credentials/api-keys?frameUrl=%2Fconsole%2Fproject%2Fapi-keys%3Fx-target-region%3Dus1). 
2) Create a new TiML App in the Twilio Console [here](https://console.twilio.com/us1/develop/voice/manage/twiml-apps?frameUrl=%2Fconsole%2Fvoice%2Ftwiml%2Fapps%3Fx-target-region%3Dus1).
3) Create a .env file which contains all necessary variables according to the .env.example attributes. 

## Local Development
To run this locally, you should have installed both the [Twilio CLI](https://www.twilio.com/docs/twilio-cli/quickstart) and the associated [Twilio Servless Toolkit Plugin](https://www.twilio.com/docs/labs/serverless-toolkit/getting-started). You can then get the functions running locally with the following command:

```twilio serverless:start```

If you would like to make the functions available via a public url, you can also easily establish an ngrok tunnel with the following command:

```twilio serverless:start --ngrok=[ngrok subdomain] ```

## Deployment
To deploy the functions to your Twilio account, make sure that you are logged into the account profile of the desired destination and then run the following command:

```twilio serverless:deploy```

You should be able to see the deployed functioned within the Twilio Console [here](https://console.twilio.com/us1/develop/functions/services?frameUrl=%2Fconsole%2Ffunctions%2Foverview%2Fservices%3Fx-target-region%3Dus1).
