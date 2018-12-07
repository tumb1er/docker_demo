FROM python:3.6

RUN apt-get update && apt-get upgrade -y && apt-get install -y
RUN apt-get install -y apt-utils aptitude

RUN apt-get install -y vim wget postgresql-client
RUN apt-get install -y cron python-imaging build-essential libgmp3-dev python3-dev

ADD ./requirements /app/requirements
WORKDIR /app/requirements
RUN pip install -r /app/requirements/develop.txt

ADD ./compose/common/wait-for-it.sh /app/wait-for-it.sh
ADD ./compose/django/start-django-dev.sh /app/start-django-dev.sh
RUN chmod +x /app/*.sh

ADD ./src /app/src
WORKDIR /app/src
