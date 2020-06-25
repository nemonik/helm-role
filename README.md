# Helm Ansible role

![Basic role syntax check](https://github.com/nemonik/helm-role/workflows/Basic%20role%20syntax%20check/badge.svg)

An Ansible role used to install [Helm CLI](https://github.com/drone/helm-cli). Verified to work on CentOS 7, Alpine 3.10 and Ubuntu Bionic instances.

## Requirements

A CentOS 7, Alpine 3.10 or Ubuntu Bionic base image.

## Role Variables

| Variable          | Required | Default                                                          | Choices        | Comments                                                          |
|-------------------|----------|------------------------------------------------------------------|----------------|-------------------------------------------------------------------|
| default_retries   | yes      | 60                                                               | Integer value  | Default number of retries                                         |
| default_delay     | yes      | 60                                                               | Integer value  | Default delay in seconds between retries                          |
| helm_cli_version  | yes      | 3.2.4                                                            | String version | The release to install from https://github.com/helm/helm/releases |
| helm_cli_checksum | yes      | 018f9908cb950701a5d59e757653a790c66d8eda288625dbb185354ca6f41f6b | String value   | The checksum matching the release                                 |
| cache_path        | no       | /tmp                                                             | String path    | used to cache drone cli tar ball                                  |

## Example Playbook

An example can be found used in my Hands-on DevOps course's [box/ansible/box-playbook-1.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/box/ansible/box-playbook-1.yml).

```
- hosts: boxes
  connection: local
  remote_user: vagrant
  roles:
    - common
    - helm-cli
```

For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>
