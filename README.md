<!--
SPDX-FileCopyrightText: 2022 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2022 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

# Ansible Role: Research Software Directory (RSD-as-a-service)

Setting up the [Research Software Directory](https://github.com/research-software-directory/RSD-as-a-service)
using Ansible.

Currently [supported platforms](meta/main.yml) are:
* Ubuntu 20.04 LTS
* Ubuntu 22.04 LTS

## Requirements

* [`docker`](https://pypi.org/project/docker/) (Docker SDK for Python)
* [`docker-compose`](https://pypi.org/project/docker-compose/)

## Role Variables

- `rsd_repo_url`
  - Default: `https://github.com/research-software-directory/research-software-directory.git`
  - Description: The RSD git repository URL.
- `rsd_working_directory`
  - Default: `/opt/rsd`
  - Description: The path where the RSD repository will be checked out.
- `rsd_version`
  - Default: `main`
  - Description: What version of the repository to check out.
- `rsd_dependencies`
  - Default: `["docker", "docker-compose"]`
  - Description: List of required python modules.
- `rsd_environment_file`
  - Default: `rsd-secrets.env`
  - Description: Inventory specific environment file
- `rsd_docker_compose_template_file`
  - Default: `docker-compose.yml.j2`
  - Description: Template file for docker-compose.yml
- `rsd_container_registry_path`
  - Default: `ghcr.io/research-software-directory/rsd-saas`
  - Description: Path to the container registry from where the images are pulled
- `rsd_nginx_config_template`
  - Default: `nginx.conf.j2`
  - Description: Template file for Nginx configuration
- `rsd_handle_tls_files`
  - Default: `true`
  - Description: Whether the role should copy TLS files to the target host.
- `rsd_tls_cert_file`
  - Default: `''`
  - Description: TLS certificate file
- `rsd_tls_key_file`
  - Default: `''`
  - Description: TLS key file
- `rsd_tls_cert_path`
  - Default: `/etc/ssl/certs/rsd.pem`
  - Description: Absolute destination path for TLS certificate file
- `rsd_tls_key_path`
  - Default: `/etc/ssl/private/rsd.key`
  - Description: Absolute destination path for TLS key file
- `rsd_nginx_dhparam_file`
  - Default: `''`
  - Description: File with DH parameters for nginx
- `rsd_nginx_dhparam_file_path`
  - Default: `"/opt/rsd/dhparam.pem"`
  - Description: Absolute destination path for DH parameters file

### RSD Env Variables
- `rsd_domain`
  - Default: `localhost`
  - Description: RSD Domain
- `rsd_ssl_domains`
  - Default: `localhost`
  - Description: RSD SSL Domains
- `rsd_gh_access_token`
  - Default: `changeme`
  - Description: GitHub personal access token
- `rsd_jwt_secret`
  - Default: `changeme`
  - Description: JSON web token secret to generate/verify tokens
- `rsd_zenodo_access_token`
  - Default: `changeme`
  - Description: Zenodo access token
- `rsd_zotero_api_key`
  - Default: `changeme`
  - Description: Zotero API key
- `rsd_zotero_library`
  - Default: `changeme`
  - Description: Zotero library name

## Dependencies

The Research Software Directory requires `docker` and `docker-compose` to be
available on the system. This role has been successfully used together with the
following Ansible roles:
* Docker - [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker)
* Pip - [geerlingguy.pip](https://galaxy.ansible.com/geerlingguy/pip)

## Example Playbook

```ỳaml
- hosts: servers
  roles:
     - { role: hifis.rsd }
```

## License

[Apache-2.0](LICENSES/Apache-2.0.txt)

## Author Information

This role was created by [HIFIS Software Services](https://www.hifis.net/).

## Contributors

We would like to thank and give credits to the following contributors of this
project:

* [tharun634](https://github.com/tharun634) 
