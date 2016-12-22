# EMBERS-Client
EMBERS client to receive messages sent from HTTP, CoAP and MQTT.

This client will connect to EMBERS and will automatically receive the messages sent using HTTP, CoAP or MQTT to a defined gateway.REA

## Installation

#### Requirements
1 - Run `pip install -r requirements.txt`;

#### Gateway
2 - Run `curl -X POST -d "type=GATEWAY_NAME" http://msg2.embers.citibrain.com/devices` in order to create your gateway. This will return the gateway uuid and token that you will need for the constants file;

** If you don't want to create a gateway, you can simply use the one already provided in the constants file. **

3 - If you created your own gateway you need to update the constants file with the correspondent credentials (uuid and token)

`HOST = "broker.embers.citibrain.com"`

`CREDENTIALS = {`
`"uuid": "gateway_uuid",`
`"token": "gateway_token",`
`}`

#### Devices
4 - Run `curl -X POST -d "type=DEVICE_NAME" http://msg2.embers.citibrain.com/devices` in order to create your device that will send messages. This will return the device uuid and token that you will need to send messages;

#### Run EMBERS-Client
5 - Run EMBERS-Client with `python embers_client.py` in order to start the client;

#### Send messages to the gateway

6 - You can send messages using one of our publishers.

