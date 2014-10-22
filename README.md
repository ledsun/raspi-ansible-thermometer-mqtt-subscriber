# raspi-ansible-thermometer-mqtt-subscriber


An ansible playbook for a RaspberryPi thermometer MQTT subscriber.

## Install

From a shell on the PC to setup the RaspberryPi:

```
git clone git@github.com:ledsun/raspi-ansible-thermometer.git
```

## Setup
### hosts
Copy `hosts.example`
```
cp hosts.example hosts
```

Edit the ip address of the RaspberryPi in the `hosts` file.

### mqttcfg
Copy `tasks/mqttclicfg.yml.example`
```
cp tasks/mqttclicfg.yml.example tasks/mqttclicfg.yml
```

Edit the account and the password for sango in the `tasks/mqttclicfg.yml` file.

Encript `task/mqttcfg.yml` include secrets to connect MQTT broker with ansible-vault.
```
ansible-vault encrypt tasks/mqttclicfg.yml
```

## Executing

From a shell on the PC to setup the RaspberryPi:

```
ansible-playbook -i hosts -u pi -k -c paramiko playbook.yml --ask-vault-pass
```

Input SSH password and Vault password.

## Assumptions

* RaspberryPi Type B 512MB
* Raspian (2014-09-09-wheezy-raspbian.img)
* USB thermometer-528018
* MQTT as a Service sango (MQTT Broker)

## Reference

* [jschairb/raspi-ansible](https://github.com/jschairb/raspi-ansible)

## License

See [LICENSE](https://github.com/ledsun/raspi-ansible-thermometer-mqtt-subscriber/blob/master/LICENSE).
