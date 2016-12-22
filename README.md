# EMBERS-Client
EMBERS client to receive messages sent using HTTP, CoAP and MQTT protocols.

## About
This client allows you to create a communication using EMBERS, so that you can receive messages sent from devices using HTTP, CoAP or MQTT protocols to a defined gateway.

## Installation

#### Requirements
Run `pip install -r requirements.txt`;

#### Gateway
The gateway is used in order to receive messages sent from devices. In order to create a new gateway you just need to run the follow:

`curl -X POST -d "type=GATEWAY_NAME" http://msg2.embers.citibrain.com/devices` 

This will return the gateway uuid and token, that you will need use as credentials for the constants file:

`CREDENTIALS = {
"uuid": "gateway_uuid",
"token": "gateway_token"
}`

#### Device(s)
The devices are used to send messages to a defined gateway. In order to create a new device you just need to run the follow:

`curl -X POST -d "type=DEVICE_NAME" http://msg2.embers.citibrain.com/devices`

This will return the device uuid and token that you will need to send messages from them to the gateway;

#### Run EMBERS-Client

After creating a gateway, device(s) and cunfiguring the constants file (with gateway uuid and token), you are able to send and receive messages usin EMBERS. For that, you just need to run  `python embers_client.py` in order to start the EMBERS-client that will receive the messages sent from devices;

In order to send messages from devices to the gateway, you just need to use one of our publishers.