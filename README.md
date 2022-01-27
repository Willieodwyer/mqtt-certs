# mqtt-certs
mqtt mosquitto cert generator

`./generate-CA.sh broker`

`./generate-CA.sh client client`


mosquitto: `mosquitto -v -c mosquitto.conf`

sub:
`mosquitto_sub -p 8883 --cafile ca.crt --cert client.crt --key client.key -h localhost -t /world`

pub:
`mosquitto_pub -p 8883 --cafile ca.crt --cert client.crt --key client.key -h localhost -t /world -m "$(date)" `
