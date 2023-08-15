# pull official base image
FROM python:3.11.4-slim-buster

# set work directory
WORKDIR /src

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install system dependencies
RUN apt-get update && apt-get install -y netcat

# install dependencies
RUN pip install --upgrade pip
COPY ./requirements .
RUN pip install -r ./local.txt

# copy project
COPY . .

# run entrypoint.sh
ENTRYPOINT ["/src/entrypoint.sh"]
