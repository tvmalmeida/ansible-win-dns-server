# ansible-win-dns-server

Playbook focused on DNS record management. For now, only A and PTR type records are part of the scope.

**Table of Contents**

- [Windows DNS Playbooks](#)
  * [Introduction](#introduction)
  * [Ensure dns record](#ensure-dns-record)
  * [Authors](#authors)

# Introduction

The purpose of this repository is include a variety of Ansible playbooks to manage dns resource records in MS Windows servers.

## ensure-dns-record

This playbook aims to be used to ensure the state present or absent of resource records in windows dns server.  

This playbook was developed considering the following scenario:
 - Winodws DNS Server;

**Variables**

To run this playbook you must define the following extra variables:
```bash
node_group: ns1.domain.com # node or group of Windows DNS Server.
dns_domain: "your.domain.com"
dns_rr_name: "vm-test01"
dns_rr_type: "A"
dns_rr_value: "w.x.y.z" # only when dns_rr_state is "present"
dns_rr_state: "present" # present or absent
```

***Ad hoc command for local development***

`ansible-playbook -i development.yml ensure-dns-record.yml -e @extra-vars/win-dns-record-dev.yml -vvv`

Make sure you have the `development.yml` file as inventory.

## Authors

 - Thiago Vinícius de Melo Almeida <@tvmalmeida>
 - Geraldo Avelino de Oliveira Neto <@gaoneto>
