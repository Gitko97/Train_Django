FROM python:3.7.4

ENV DJANGO_SETTINGS_MODULE=config.settings.server

# install dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# copy project
COPY . .
WORKDIR .


COPY ./entrypoint.sh /
ENTRYPOINT ["sh", "/entrypoint.sh"]

#CMD ["gunicorn", "--bind", "0.0.0.0:8000", "config.wsgi:application"]