FROM ubuntu:16.04
RUN apt-get update && apt-get install -y  build-essential python-virtualenv virtualenvwrapper libpq-dev python-dev libtiff5-dev libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev libffi-dev libssl-dev uwsgi nginx supervisor vim uwsgi-plugin-python
VOLUME  /project
RUN virtualenv /var/venv
COPY project/ /project/example-app
RUN cd /project/example-app && /var/venv/bin/pip install -r requirements.txt
RUN /var/venv/bin/pip install uwsgi
WORKDIR /project/example-app/
CMD ["/var/venv/bin/uwsgi", "--http", "0.0.0.0:8000", "--module", "example-app.wsgi", "--uid", "www-data", "--gid", "www-data", "--enable-threads"]
EXPOSE 8000