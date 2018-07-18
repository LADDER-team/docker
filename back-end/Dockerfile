FROM python:3.6.4

WORKDIR /root/ladder

EXPOSE 8000

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
                Pillow

COPY run.sh /root/ladder/run.sh

ENTRYPOINT ["bash", "/root/ladder/run.sh"]
