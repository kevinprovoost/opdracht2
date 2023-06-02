# Ansible Role: generate_ssl_cert_and_run_ha

This Ansible role is responsible for generating a self-signed SSL certificate and running a Home Assistant Docker container.

## Requirements

None.

## Role Variables

This role uses the following variables, defined in `vars/main.yml`:

```yml
key_size: 2048
key_type: RSA
country_name: BE
```

Server hostname is defined in the main playbook.

## Dependencies

This role needs to be ran after the `setup_packages` role and before the `configure_nginx_and_ha` role.

## Example Playbook

```yml
- hosts: servers
  roles:
     - { role: username.generate_ssl_cert_and_run_ha }
```

## License

This project is licensed under the MIT License.

## Author Information

This role was created in 2023 by [Kevin Provoost](mailto:kevin.provoost@student.howest.be).