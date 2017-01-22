docker-service-deploy
=========

Deploys a docker service by copying a docker-compose.yml file and needed external file dependencies onto the host.

Role Variables
--------------

```yml
docker_service_deploy_project_dir: /docker/nginx
docker_service_deploy_src: docker-compose.yml
docker_service_deploy_pull: yes
docker_service_deploy_additional_files:
  - nginx.crt
  - nginx.key
```

Dependencies
------------

* angstwad.docker_ubuntu

Example Playbook
----------------

```yml

---
- hosts: foo.bar
  become: true
  roles:
    - role: docker-service-deploy
      project_dir: /docker/gitlab
      additional_files:
        - config.toml

    - role: docker-service-deploy
      docker_compose_src: artifactory-docker-compose.yml
      project_dir: /docker/artifactory
```
License
-------

Apache v2.0