FROM ansible/ubuntu14.04-ansible:stable

ADD .. /srv/ansible
WORKDIR /srv/ansible

RUN ansible-playbook mezzanine-container.yml -c local

RUN mkdir /srv
WORKDIR /srv/mezzanine

EXPOSE 8000
ENTRYPOINT ["/usr/local/bin/gunicorn_django", "-c", "gunicorn.conf.py"]
