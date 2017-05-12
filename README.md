# Fuga Ansible Demo

Source code for the Demo given by the Fuga team to deploy instances using Ansible.

## Demo

The demo starts with an empty Fuga account and creates networking, security groups and instances. These will be configured to form a loadbalancer and two webservers. Everything is done using an Ansible playbook.

## Running the demo

If you want to run the demo yourself you need to have ansible installed and a working Fuga account, you can create a Fuga account on https://fuga.io/.
Clone this repo:

```bash
$ git clone https://github.com/dporru/dhpa-techfest-2017-fuga-demo
$ cd dhpa-techfest-2017-fuga-demo
```

Rename the `openrc.example` to `openrc.sh` and fill the missing details. Finally run the demo:

```bash
$ source openrc.sh
$ ansible-playbook deploy.yml
```

## Adding servers

If you want to change the amount of servers, you can change the `fuga_instances` list in `host_vars/localhost.yml`. To deploy server changes you only need to run the `configure` tag.

```bash
$ ansible-playbook deploy.yml -t configure
```

## Watch the status

Ansible will create a `status.html` file. This contains an iframe which points to the loadbalancer ip address and refreshes itself every second.

## Clean up

To clean everything up, run the `clear.yml` playbook.

```bash
$ ansible-playbook clear.yml
```
