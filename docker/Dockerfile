FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y --no-install-recommends python3-gdal python3-rtree python3-bottle python3-gunicorn bc unrar
RUN rm -f /var/cache/apt/archives/*.deb /var/lib/apt/lists/*.deb

RUN mkdir /code
ADD . /code/

WORKDIR /code

CMD python3 server.py

EXPOSE 8080
