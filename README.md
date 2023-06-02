# Ansible Playbook for Home Assistant on a Debian Server
-------------------------------------------------------
This Ansible playbook is designed to set up Home Assistant on a Debian server. It consists of three roles: 

1. `setup_packages`
2. `configure_ssl_and_ha`
3. `configure_nginx_and_ha`

These roles install necessary packages, configure SSL certificates, set up Home Assistant, and configure Nginx to serve Home Assistant. 

## Requirements
--------------
1. A Debian-based Linux distribution.
2. Ansible 2.9.0 or higher.

## Roles
--------
- `setup_packages`: This role installs necessary packages, sets up a specific directory and user for Docker.

- `configure_ssl_and_ha`: This role generates OpenSSL keys, CSR, and a self-signed certificate, and then runs a Home Assistant Docker container.

- `configure_nginx_and_ha`: This role configures Nginx to serve Home Assistant.

More details about each role can be found in their individual READMEs.

## Playbook Variables
---------------------
This playbook uses the following variable:

```yml
server_hostname: websrv.com
```

## Example Playbook Execution
-----------------------------
To run this playbook, use the following command:

\```bash
ansible-playbook main.yml -K
\```
After this command, enter your sudo password for the nodes.

Make sure to replace `inventory.ini` in the directory to your actual inventory file.

## License
-------
This project is licensed under the MIT License.

## Author Information
----------------------
This role was created in 2023 by [Kevin Provoost](mailto:kevin.provoost@student.howest.be).