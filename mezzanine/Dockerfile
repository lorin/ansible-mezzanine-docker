FROM ansible/ubuntu14.04-ansible:stable

ADD ansible /srv/ansible
WORKDIR /srv/ansible

RUN ansible-playbook mezzanine-container.yml -c local

WORKDIR /srv/project

EXPOSE 8000
CMD ["/usr/local/bin/gunicorn_django", "-c", "gunicorn.conf.py"]
