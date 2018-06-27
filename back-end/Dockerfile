FROM python:3.6.4
WORKDIR /root/ladder
EXPOSE 8000
ARG GIT_REF=master
RUN git clone -b ${GIT_REF} https://github.com/LADDER-team/ladder.git /root/ladder && \
    pip install django \
                django-crispy-forms \
                djangorestframework \
                django-filter \
                djangorestframework-jwt \
                Pillow && \
    python manage.py migrate
ENTRYPOINT ["python", "manage.py", "runserver", "0.0.0.0:8000"]
