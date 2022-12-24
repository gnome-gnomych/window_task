FROM python:3.10-bullseye

RUN apt install curl

RUN curl -sL https://deb.nodesource.com/setup_16.x | bash -

RUN apt-get install nodejs-legacy

RUN npm install -g configurable-http-proxy

RUN python3 -m pip install jupyterhub

RUN python3 -m pip install --upgrade notebook

COPY config.py config.py

EXPOSE 8000

CMD ["jupyterhub", "-f", "config.py"]

