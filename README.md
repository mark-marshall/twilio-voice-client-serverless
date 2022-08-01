# Severless Functions to support Twilio Voice Client
This is an implementation of a backend service that can be used to support a Twilio Voice Client application. It is comprised of 3 endpoints:

1) A /token endpoint which expects to receive an identity parameter in the request and returns a Twilio token with a Voice Grant.
2) A /make call endpoint which acts as a TwiML App that is hit whenver the client makes an outbound call. It connects the call with a recpient.
3) A /receive call endpoint which the inbound Twilio number is pointed to and connects the caller with the client.

