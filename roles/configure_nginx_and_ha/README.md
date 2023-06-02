# Ansible Role: configure_nginx_and_ha

This Ansible role configures Nginx as a reverse proxy for Home Assistant running in a Docker container.

## Requirements

None.

## Role Variables

Server hostname is defined in the main playbook.

## Dependencies

This role needs to be ran after the `setup_packages` and `generate_ssl_cert_and_run_ha` roles, in that order.

## Example Playbook

This role uses the following variables, defined in the playbook directory in `main.yml`:

```yml
- hosts: servers
  roles:
     - { role: username.configure_nginx_and_ha }
```

## License

This project is licensed under the MIT License.

## Author Information

This role was created in 2023 by [Kevin Provoost](mailto:kevin.provoost@student.howest.be).

## Tasks Included

- Configure Nginx server block
- Create Nginx server block symbolic link
- Wait for Home Assistant `configuration.yaml` to exist
- Add http configuration block to `configuration.yaml`
- Restart Nginx
- Restart Home Assistant Docker container
- Pause for 10 seconds
- Check website
- Print result