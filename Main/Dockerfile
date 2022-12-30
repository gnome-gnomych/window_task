FROM python:3.10-bullseye

ARG NOTEBOOKS_FROM=/from
ARG HUB_PATH=/admin

RUN apt install curl

RUN curl -sL https://deb.nodesource.com/setup_16.x | bash -

RUN apt-get install nodejs-legacy

RUN npm install -g configurable-http-proxy

RUN python3 -m pip install jupyterhub

RUN python3 -m pip install --upgrade notebook

RUN useradd -ms /bin/bash admin

RUN echo 'admin:admin' | chpasswd

COPY config.py config.py

COPY ${NOTEBOOKS_FROM} /home/${HUB_PATH}

EXPOSE 8000

CMD jupyterhub -f config.py
