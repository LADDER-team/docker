FROM python:3.6.4

WORKDIR /root/ladder

EXPOSE 80

ARG GIT_REF=master

RUN git clone -b ${GIT_REF} https://github.com/LADDER-team/ladder-api-server.git /root/ladder && \
    pip install --upgrade pip && \
    pip install django \
                django-crispy-forms \
                djangorestframework \
                django-filter \
                djangorestframework-jwt \
                django-cors-headers \
                psycopg2 \
                Pillow \
                uwsgi && \
    apt-get update && \
    apt-get install -y nginx

COPY run.sh /root/ladder/
COPY wsgi.ini /root/ladder/
COPY uwsgi_params /root/ladder/
COPY ladder-nginx.conf /etc/nginx/sites-enabled/

CMD ["bash", "/root/ladder/run.sh"]
