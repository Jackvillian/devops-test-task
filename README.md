
# The test task for the DevOps engineer candidates

Create an Ansible role+playbook to bootstrap the sample Django project, use the Ansible-Vault to keep secrets safe.

## Check docker exists, install if not

Role: docker

Install latest the docker

## Create linked docker containers with Django sample app and Postgres
Minimum set of roles

Role: postgres

Run container with persistent volume mounted.

Create a container, create DB and user - django.

Role: django

Run container based on debian:stable

Determine and install all dependencies. 

Deploy sample project and run all build tasks. 

Put settings.py template with decrypted secrets to project root_dir.
Then, execute app with the uwsgi.

Source code: https://github.com/kirpit/django-sample-app

Push final project to your GitHub public repository.

