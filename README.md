<!--
SPDX-FileCopyrightText: 2022 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2022 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)
SPDX-FileCopyrightText: 2022 Helmholtz Centre Potsdam - GFZ German Research Centre for Geosciences

SPDX-License-Identifier: Apache-2.0
-->

# Ansible Role: Research Software Directory (RSD-as-a-service)

[![CI status](https://github.com/hifis-net/ansible-role-rsd/actions/workflows/ci.yml/badge.svg)](https://github.com/hifis-net/ansible-role-rsd/actions/workflows/ci.yml)
[![Ansible Role: hifis.unattended_upgrades](https://img.shields.io/ansible/role/58679)](https://galaxy.ansible.com/hifis/rsd)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/58679)](https://galaxy.ansible.com/hifis/rsd)
[![Ansible Role Downloads](https://img.shields.io/ansible/role/d/58679)](https://galaxy.ansible.com/hifis/rsd)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7008976.svg)](https://doi.org/10.5281/zenodo.7008976)

Setting up the [Research Software Directory](https://github.com/research-software-directory/RSD-as-a-service)
using Ansible.

Currently [supported platforms](meta/main.yml) are:
* Ubuntu 20.04 LTS
* Ubuntu 22.04 LTS

## Requirements

* [`docker`](https://pypi.org/project/docker/) (Docker SDK for Python)
* [`docker-compose`](https://pypi.org/project/docker-compose/)

## Role Variables

- `rsd_dependencies`
  - Default: `["docker", "docker-compose"]`
  - Description: List of required python modules.
- `rsd_working_directory`
  - Default: `"/opt/rsd"`
  - Description: The path where the RSD repository will be checked out.
- `rsd_version`
  - Default: `"latest"`
  - Description: What version of the RSD-as-a-service container images to deploy (image tag name).
    If `latest` is used the container images will always be pulled prior starting the application.
- `rsd_container_registry_path`
  - Default: `"ghcr.io/hifis-net/rsd-saas"`
  - Description: Path to the container registry from where the images are pulled.
- `rsd_environment_file`
  - Default: `"rsd-secrets.env"`
  - Description: Inventory specific environment file.
- `rsd_docker_compose_cmd`
  - Default: `"docker-compose"`
  - Description: Docker Compose command used to validate docker-compose.yml.
- `rsd_docker_compose_template_file`
  - Default: `"docker-compose.yml.j2"`
  - Description: Template file for docker-compose.yml.
- `rsd_nginx_config_template`
  - Default: `"nginx.conf.j2"`
  - Description: Template file for Nginx configuration.
- `rsd_tls_cert_path`
  - Default: `"/etc/ssl/certs/rsd.pem"`
  - Description: Absolute destination path for TLS certificate file.
- `rsd_tls_key_path`
  - Default: `"/etc/ssl/private/rsd.key"`
  - Description: Absolute destination path for TLS key file.
- `rsd_nginx_dhparam_file_path`
  - Default: `"/etc/ssl/private/dhparam.pem"`
  - Description: Absolute destination path for DH parameters file.
- `rsd_prune_volumes`
  - Default: `false`
  - Description: Set to `true` to remove docker data volumes (**this will force container recreation**).
- `rsd_migrate_spotlights`
  - Default: `false`
  - Description: Set to `true` to migrate the software spotlights from hifis.net into the RSD (Helmholtz theme only).
- `rsd_spotlight_migration_image`
  - Default: `"ghcr.io/hifis-net/rsd-spotlight-migration:v1.0.0"`
  - Description: Container image for software spotlights migration

### RSD Env Variables
- `rsd_compose_project_name`
  - Default: `"rsd"`
  - Description: Define the [Compose project name](https://docs.docker.com/compose/reference/envvars/#compose_project_name),
    if you are running different versions of the RSD.
- `rsd_domain`
  - Default: `"localhost"`
  - Description: Domain name under which the RSD should be accessible.
- `rsd_auth_providers`
  - Default: `"SURFCONEXT;HELMHOLTZAAI"`
  - Description: Semicolon-separated list of supported OpenID auth providers.
- `rsd_admin_email_list`
  - Default: `None`
  - Description: Semicolon-separated list of user email addresses (exact match incl. the letter casing) of RSD admins.
- `rsd_auth_user_mail_whitelist`
  - Default: `None`
  - Description: Semicolon-separated list of user email addresses which are allowed to log into the RSD.
- `rsd_hgfaai_client_id`
  - Default: `"rsd-dev"`
  - Description: Public Helmholtz AAI client ID.
- `rsd_hgfaai_client_secret`
  - Default: `"changeme"`
  - Description: Helmholtz AAI client secret.
- `rsd_hgfaai_well_known_url`
  - Default: `"https://login-dev.helmholtz.de/oauth2/.well-known/openid-configuration"`
  - Description: Helmholtz AAI well known URL.
- `rsd_hgfaai_token_url`
  - Default: `"https://login-dev.helmholtz.de/oauth2/token"`
  - Description: Helmholtz AAI token URL.
- `rsd_hgfaai_allow_external_users`
  - Default: `false`
  - Description: Set to `true` to allow users from non-Helmholtz centres or social IdPs.
- `rsd_postgres_password`
  - Default: `"changeme"`
  - Description: Postgres password.
- `rsd_postgres_authenticator_password`
  - Default: `"ChangeMe"`
  - Description: Postgres authenticator password used by the backend (**should be different from `rsd_postgres_password`**).
- `rsd_max_requests_github`
  - Default: `"6"`
  - Description: Maximum number of requests to the GitHub API per run.
- `rsd_max_requests_gitlab`
  - Default: `"6"`
  - Description: Maximum number of requests to the GitLab API per run.
- `rsd_max_requests_doi`
  - Default: `"6"`
  - Description: Maximum number of mentions to scrape per run.
- `rsd_surfconext_client_secret`
  - Default: `"changeme"`
  - Description: SurfConext client secret.
- `rsd_gh_access_token`
  - Default: `"changeme"`
  - Description: GitHub personal access token.
- `rsd_jwt_secret`
  - Default: `"changemeChangemeChangemeChangeme"`
  - Description: JSON web token secret with **at least 32 characters** to generate/verify tokens.
- `rsd_zenodo_access_token`
  - Default: `"changeme"`
  - Description: Zenodo access token.
- `rsd_crossref_contact_email`
  - Default: `""`
  - Description: Email address that Crossref can contact you with to comply with their "polite" policy.
- `rsd_hotjar_id`
  - Default: `""`
  - Description: ID for Hotjar Tracking Code (needs to be a number).
- `rsd_matomo_url`
  - Default: `""`
  - Description: Tracking URL (should end with a trailing slash)
- `rsd_matomo_id`
  - Default: `""`
  - Description: Matomo ID for the corresponding tracking URL

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
