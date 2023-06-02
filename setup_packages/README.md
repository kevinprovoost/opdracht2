# Ansible Role: install_packages_and_setup_user

This Ansible role is responsible for installing required packages, setting up a specific directory and user for Docker.

## Requirements

None.

## Role Variables

This role uses the following variables, defined in `vars/main.yml`:

```yml
package_list:
  - docker.io
  - nginx
  - python3-pip

pip_packages:
  - pyopenssl
  - docker-py
```

Server hostname is defined in the main playbook.

## Dependencies

This role needs to be ran before the `configure_ssl_and_ha` and `configure_nginx_and_ha` role.

## Example Playbook

```yml
- hosts: servers
  roles:
     - { role: username.setup_packages }
```

## License

This project is licensed under the MIT License.

## Author Information

This role was created in 2023 by [Kevin Provoost](mailto:kevin.provoost@student.howest.be).

## Tasks Included

- Install Nginx and pip packages
- Create a specific directory (`haconfig`)
- Install pip packages `pyopenssl` and `docker-py`
- Create Docker group
- Add user `kevin` to Docker group