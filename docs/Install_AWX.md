
# AWX Installation Instructions

How to install this clustered AWX setup.


## Provision the Servers

Provision at least 3 Debian 11 or Ubuntu 22.04 server with >=8GB RAM, disabled swap and a public IP, then setup SSH access to root@{{ awx_url }} account, these will be our Rancher/AWX servers.

Alternatively you can provision these servers and configure the DNS automatically using DigitalOcean/Cloudflare by running this playbook with the 'provision' tag:

`$ ansible-playbook -v -i ./inventory/hosts -t "provision" setup.yml`

After your finished you can delete these servers/records with the 'teardown' tag:

`$ ansible-playbook -v -i ./inventory/hosts -t "teardown" setup.yml`


## Setup DNS Entries for it

1) A/AAAA record for awx1.example.org to the servers IP.

2) optionally, an A/AAAA record for rancher.example.org to the servers IP, 
    or a CNAME record for it pointing to awx.example.org.


## Install

1) Install the following ansible-galaxy packages on the controller:
```
$ ansible-galaxy collection install --force awx.awx:21.9.0
$ ansible-galaxy collection install community.grafana
$ ansible-galaxy collection install community.digitalocean
```


2) Edit hosts into: [./inventory/hosts](./inventory/hosts)

Create folder for each host at: ./inventory/host_vars/

Record each hosts variables into each hosts ./inventory/host_vars/awx1.example.org/vars.yml file.


3) Run the playbook with the following tags:

`$ ansible-playbook -v -i ./inventory/hosts -t "rke2-setup" setup.yml`
