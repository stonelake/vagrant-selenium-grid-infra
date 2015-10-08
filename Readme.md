Introduction
----------------

Provides basic selenium grid infratstucture (1 hub and 2 nodes).

Basd on:
 - https://github.com/jesg/systemd-units/tree/master/selenium
 - https://github.com/bcoca/ansible-selenium-role

Supported images:
 - Centos 7

Supported browser: 
 - Firefox

Usage
-----------------

1. Install vagrant, ansible and provider (virtualbox)

2. Start hub
    ```bash
    $ vagrant up hub

    ```

3. Sart nodes
    ```bash
    $ vagrant up node1
    $ vagrant up node2
    ```

By defaut the following IP addresses will be assigned: 
 ``` bash
 hub_ip = "192.168.17.10"
 node1_ip = "192.168.17.11"
 node2_ip = "192.168.17.12"
 ```
 
This can be changed in the Vagrantfile.


Getting logs
-----------------

To get logs the _journalctl_ can be used. For hub service:

```bash
$ vagrant ssh hub
$ sudo journalctl -f -u selenium.hub
```

For node service

```bash
$ vagrant ssh node1
$ sudo journalctl -f -u selenium.node
```
