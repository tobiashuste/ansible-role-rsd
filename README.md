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
- `rsd_tls_cert_file`
  - Default: `rsd.pem`
  - Description: TLS certificate file
- `rsd_tls_key_file`
  - Default: `rsd.key`
  - Description: TLS key file
- `rsd_container_registry_path`
  - Default: `ghcr.io/research-software-directory/rsd-saas`
  - Description: Path to the container registry from where the images are pulled

### RSD Env Variables
- `rsd_domain`
  - Default: `localhost`
  - Description: RSD Domain
- `rsd_auth_providers`
  - Default: `SURFCONEXT;HELMHOLTZAAI`
  - Description: Semicolon-separated list of supported OpenID auth providers
- `rsd_auth_user_mail_whitelist`
  - Default: `''`
  - Description: Semicolon-separated list of user email addresses which are allowed to log into the RSD
- `rsd_hgfaai_client_id`
  - Default: `rsd-dev`
  - Description: Public Helmholtz AAI client ID
- `rsd_hgfaai_client_secret`
  - Default: `changeme`
  - Description: Helmholtz AAI client secret
- `rsd_hgfaai_well_known_url`
  - Default: `https://login-dev.helmholtz.de/oauth2/.well-known/openid-configuration`
  - Description: Helmholtz AAI well known URL
- `rsd_hgfaai_token_url`
  - Default: `https://login-dev.helmholtz.de/oauth2/token`
  - Description: Helmholtz AAI token URL
- `rsd_postgres_password`
  - Default: `changeme`
  - Description: Postgres passwort
- `rsd_surfconext_client_secret`
  - Default: `changeme`
  - Description: SurfConext client secret
- `rsd_gh_access_token`
  - Default: `changeme`
  - Description: GitHub personal access token
- `rsd_jwt_secret`
  - Default: `changeme`
  - Description: JSON web token secret to generate/verify tokens
- `rsd_zenodo_access_token`
  - Default: `changeme`
  - Description: Zenodo access token
- `rsd_crossref_contact_email`
  - Default: `''`
  - Description: Email address that Crossref can contact you with to comply with their "polite" policy
- `rsd_hotjar_id`
  - Default: `''`
  - Description: ID for Hotjar Tracking Code (needs to be a number)

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
