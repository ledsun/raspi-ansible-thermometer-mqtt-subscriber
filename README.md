# raspi-ansible-thermometer-mqtt-subscriber


An ansible playbook for a RaspberryPi thermometer MQTT subscriber.

## Install

From a shell on the PC to setup the RaspberryPi:

```
git clone git@github.com:ledsun/raspi-ansible-thermometer.git
```

## Setup

Create hosts file include the ip address of the RaspberryPi like below:
```
[raspberry-pi]
192.168.111.8
```

## Executing

From a shell on the PC to setup the RaspberryPi:

```
ansible-playbook -i hosts -u pi -k -c paramiko playbook.yml --ask-vault-pass
```

Input SSH password and Vault password.

The ansible-vault is used to encrypt secrets to connect MQTT broker.

## Assumptions

* RaspberryPi Type B 512MB
* Raspian (2014-09-09-wheezy-raspbian.img)
* USB thermometer-528018
* MQTT as a Service sango (MQTT Broker)

## Credits

* [jschairb/raspi-ansible](https://github.com/jschairb/raspi-ansible/blob/master/README.md)

## License

See [LICENSE](https://github.com/jschairb/raspi-ansible/blob/master/LICENSE).
