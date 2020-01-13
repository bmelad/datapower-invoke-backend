# Invoke a backend call using GatewayScript

Using IBM DataPower Gateway, sometimes you need to handle some "complicated" RESTful services, usually each service gets a matching & processing rules, but what if you need to support different processing scenarios for the same URL with different HTTP verbs/methods?

DataPower Matching Rule object will not support the Method option for a Response rule, so here is a simple solution - just handle the whole processing flow in a request rule (using the magic of 'skip-backside' service variable).

This GatewayScript will handle the backend call and let you continue the flow with any processing action you need.

## How to use it?

1. Drag a GatewayScript processing action and select the 'invoke-backend.js' file, set the Input of the action to the relevant value.

1. Go to the Advanced tab of the GatewayScript processing action and add a parameter named 'BaseURL' with the base-url value of your backend.

#

The default timeout is 30 seconds, if you want to override this settings, just add another parameter named 'Timeout' and set the desired value in seconds.
