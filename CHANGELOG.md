# Changelog

## [v1.2.0](https://github.com/hifis-net/ansible-role-rsd/tree/v1.2.0) (2022-07-08)

[Full Changelog](https://github.com/hifis-net/ansible-role-rsd/compare/v1.1.0...v1.2.0)

**Closed issues:**

- Add option to remove existing containers and volumes [\#61](https://github.com/hifis-net/ansible-role-rsd/issues/61)
- Improve deployment by using docker-compose down + up [\#60](https://github.com/hifis-net/ansible-role-rsd/issues/60)

**Merged pull requests:**

- Add handler to restart nginx on config changes [\#65](https://github.com/hifis-net/ansible-role-rsd/pull/65) ([Normo](https://github.com/Normo))
- Update README.md [\#64](https://github.com/hifis-net/ansible-role-rsd/pull/64) ([Normo](https://github.com/Normo))
- Add handler to recreate containers on .env file changes [\#63](https://github.com/hifis-net/ansible-role-rsd/pull/63) ([Normo](https://github.com/Normo))
- Add flag to force removal of docker data volumes [\#62](https://github.com/hifis-net/ansible-role-rsd/pull/62) ([Normo](https://github.com/Normo))

## [v1.1.0](https://github.com/hifis-net/ansible-role-rsd/tree/v1.1.0) (2022-07-04)

[Full Changelog](https://github.com/hifis-net/ansible-role-rsd/compare/v1.0.0...v1.1.0)

**Implemented enhancements:**

- Use different values for POSTGRES\_PASSWORD and  POSTGRES\_AUTHENTICATOR\_PASSWORD [\#56](https://github.com/hifis-net/ansible-role-rsd/issues/56)
- Add more configurable variables for .env file [\#54](https://github.com/hifis-net/ansible-role-rsd/issues/54)

**Merged pull requests:**

- Prepare release v1.1.0 [\#59](https://github.com/hifis-net/ansible-role-rsd/pull/59) ([Normo](https://github.com/Normo))
- Add restart policy to docker-compose.yml template [\#58](https://github.com/hifis-net/ansible-role-rsd/pull/58) ([Normo](https://github.com/Normo))
- Add variable rsd\_postgres\_authenticator\_password [\#57](https://github.com/hifis-net/ansible-role-rsd/pull/57) ([Normo](https://github.com/Normo))
- Add more env variables to configure RSD [\#55](https://github.com/hifis-net/ansible-role-rsd/pull/55) ([Normo](https://github.com/Normo))

## [v1.0.0](https://github.com/hifis-net/ansible-role-rsd/tree/v1.0.0) (2022-06-29)

[Full Changelog](https://github.com/hifis-net/ansible-role-rsd/compare/v0.1.0...v1.0.0)

**Implemented enhancements:**

- Remove dependency on the inventory when copying TLS certificates [\#18](https://github.com/hifis-net/ansible-role-rsd/issues/18)
- Make RSD image registry and repository configurable [\#35](https://github.com/hifis-net/ansible-role-rsd/issues/35)
- Add github-changelog-generator params file [\#25](https://github.com/hifis-net/ansible-role-rsd/issues/25)
- Add support for Ubuntu 22.04 [\#24](https://github.com/hifis-net/ansible-role-rsd/issues/24)
- Add preflight checks [\#12](https://github.com/hifis-net/ansible-role-rsd/issues/12)
- Migrate changelog to github-changelog-generator [\#5](https://github.com/hifis-net/ansible-role-rsd/issues/5)
- Update dependencies via Dependabot [\#4](https://github.com/hifis-net/ansible-role-rsd/issues/4)
- Setup new RSD-as-a-service implementation [\#3](https://github.com/hifis-net/ansible-role-rsd/issues/3)
- Add role testing using molecule [\#2](https://github.com/hifis-net/ansible-role-rsd/issues/2)
- Update template files [\#45](https://github.com/hifis-net/ansible-role-rsd/pull/45) ([Normo](https://github.com/Normo))
- Test initial dry-run with molecule [\#34](https://github.com/hifis-net/ansible-role-rsd/pull/34) ([Normo](https://github.com/Normo))
- Make container registry configurable [\#36](https://github.com/hifis-net/ansible-role-rsd/pull/36) ([Normo](https://github.com/Normo))
- Add nginx configuration to enable HTTPS by default [\#31](https://github.com/hifis-net/ansible-role-rsd/pull/31) ([Normo](https://github.com/Normo))
- Add preflight checks [\#30](https://github.com/hifis-net/ansible-role-rsd/pull/30) ([Normo](https://github.com/Normo))
- Run molecule test against Ubuntu 22.04 [\#27](https://github.com/hifis-net/ansible-role-rsd/pull/27) ([Normo](https://github.com/Normo))
- Stop prepend the inventory dir name when copying TLS certificate files [\#19](https://github.com/hifis-net/ansible-role-rsd/pull/19) ([Normo](https://github.com/Normo))
- Add molecule MVP [\#11](https://github.com/hifis-net/ansible-role-rsd/pull/11) ([Normo](https://github.com/Normo))
- Migrate changelog to github-changelog-generator [\#7](https://github.com/hifis-net/ansible-role-rsd/pull/7) ([Normo](https://github.com/Normo))

**Fixed bugs:**

- Errors during preflight checks in initial dry-run [\#49](https://github.com/hifis-net/ansible-role-rsd/issues/49)
- Bug: RSD environment template file not found [\#9](https://github.com/hifis-net/ansible-role-rsd/issues/9)
- Ignore errors during initials dry-run [\#48](https://github.com/hifis-net/ansible-role-rsd/pull/48) ([Normo](https://github.com/Normo))
- Fix molecule lint [\#29](https://github.com/hifis-net/ansible-role-rsd/pull/29) ([Normo](https://github.com/Normo))

**Closed issues:**

- Change package management tool named in CONTRIBUTING guide [\#40](https://github.com/hifis-net/ansible-role-rsd/issues/40)
- Prepare release v1.0.0 [\#51](https://github.com/hifis-net/ansible-role-rsd/issues/51)

**Merged pull requests:**

- Bump ansible from 5.9.0 to 6.0.0 [\#47](https://github.com/hifis-net/ansible-role-rsd/pull/47) ([dependabot[bot]](https://github.com/apps/dependabot))
- Add jammy jellyfish to supported platforms [\#46](https://github.com/hifis-net/ansible-role-rsd/pull/46) ([Normo](https://github.com/Normo))
- License File Formatting [\#43](https://github.com/hifis-net/ansible-role-rsd/pull/43) ([Normo](https://github.com/Normo))
- Bump molecule from 3.6.1 to 4.0.0 [\#42](https://github.com/hifis-net/ansible-role-rsd/pull/42) ([dependabot[bot]](https://github.com/apps/dependabot))
- Change package management tool named in CONTRIBUTING guide [\#41](https://github.com/hifis-net/ansible-role-rsd/pull/41) ([christianhueserhzdr](https://github.com/christianhueserhzdr))
- Add contribution guide [\#39](https://github.com/hifis-net/ansible-role-rsd/pull/39) ([Normo](https://github.com/Normo))
- Bump ansible-lint from 6.2.2 to 6.3.0 [\#38](https://github.com/hifis-net/ansible-role-rsd/pull/38) ([dependabot[bot]](https://github.com/apps/dependabot))
- Bump ansible from 5.8.0 to 5.9.0 [\#37](https://github.com/hifis-net/ansible-role-rsd/pull/37) ([dependabot[bot]](https://github.com/apps/dependabot))
- Update role meta information [\#33](https://github.com/hifis-net/ansible-role-rsd/pull/33) ([Normo](https://github.com/Normo))
- Bump ansible-lint from 6.2.1 to 6.2.2 [\#32](https://github.com/hifis-net/ansible-role-rsd/pull/32) ([dependabot[bot]](https://github.com/apps/dependabot))
- Bump robertdebock/galaxy-action from 1.2.0 to 1.2.1 [\#28](https://github.com/hifis-net/ansible-role-rsd/pull/28) ([dependabot[bot]](https://github.com/apps/dependabot))
- Add params file for github-changelog-generator [\#26](https://github.com/hifis-net/ansible-role-rsd/pull/26) ([Normo](https://github.com/Normo))
- Bump reuse from 0.14.0 to 1.0.0 [\#23](https://github.com/hifis-net/ansible-role-rsd/pull/23) ([dependabot[bot]](https://github.com/apps/dependabot))
- Update requirements.yml [\#53](https://github.com/hifis-net/ansible-role-rsd/pull/53) ([Normo](https://github.com/Normo))
- Prepare release v1.0.0 [\#52](https://github.com/hifis-net/ansible-role-rsd/pull/52) ([Normo](https://github.com/Normo))
- Make role ready for production [\#50](https://github.com/hifis-net/ansible-role-rsd/pull/50) ([Normo](https://github.com/Normo))
- Upgrade python to 3.10 [\#21](https://github.com/hifis-net/ansible-role-rsd/pull/21) ([Normo](https://github.com/Normo))
- Bump ansible from 5.7.0 to 5.7.1 [\#16](https://github.com/hifis-net/ansible-role-rsd/pull/16) ([dependabot[bot]](https://github.com/apps/dependabot))
- Bump ansible from 5.6.0 to 5.7.0 [\#15](https://github.com/hifis-net/ansible-role-rsd/pull/15) ([dependabot[bot]](https://github.com/apps/dependabot))
- Set up RSD-as-a-service [\#13](https://github.com/hifis-net/ansible-role-rsd/pull/13) ([Normo](https://github.com/Normo))
- fix: make RSD env template file work [\#10](https://github.com/hifis-net/ansible-role-rsd/pull/10) ([Normo](https://github.com/Normo))
- Bump ansible from 5.5.0 to 5.6.0 [\#8](https://github.com/hifis-net/ansible-role-rsd/pull/8) ([dependabot[bot]](https://github.com/apps/dependabot))
- fixes\(\#4\): added dependabot.yml [\#6](https://github.com/hifis-net/ansible-role-rsd/pull/6) ([tharun634](https://github.com/tharun634))
- Implement lint and release workflow via GitHub actions [\#1](https://github.com/hifis-net/ansible-role-rsd/pull/1) ([Normo](https://github.com/Normo))

## [v0.1.0](https://github.com/hifis-net/ansible-role-rsd/releases/tag/v0.1.0) - 2022-04-06

### Added
Initial release of the Research Software Directory (RSD) Ansible Role.


\* *This Changelog was automatically generated by [github_changelog_generator](https://github.com/github-changelog-generator/github-changelog-generator)*
