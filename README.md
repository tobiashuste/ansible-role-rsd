<!--
SPDX-FileCopyrightText: 2022 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2022 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

# Ansible Role: Research Software Directory (RSD)

Setting up the [Research Software Directory](https://github.com/research-software-directory/research-software-directory)
using Ansible.

## Requirements

* [`docker`](https://pypi.org/project/docker/) (Docker SDK for Python)

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
- `rsd_environment_file`
  - Default: `rsd-secrets.env`
  - Description: Inventory specific environment file
- `rsd_tls_cert_file`
  - Default: `rsd.pem`
  - Description: TLS certificate file
- `rsd_tls_key_file`
  - Default: `rsd.key`
  - Description: TLS key file
- `rsd_basic_auth_hash`
  - Default: `changeme`
  - Description: Base-64 encoding of the hashed password for HTTP basic authentication

### RSD Env Variables
- `rsd_auth_gh_client_id`
  - Default: `changeme`
  - Description: GitHub OAuth application client ID
- `rsd_auth_gh_client_secret`
  - Default: `changeme`
  - Description: GitHub OAuth application client secret
- `rsd_auth_gh_organization`
  - Default: `changeme`
  - Description: GitHub organization name
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

The Research Software Directory requires `docker` and `docker-compose` to be available on the system.
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
