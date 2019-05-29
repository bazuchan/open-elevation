FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y --no-install-recommends python3-gdal python3-rtree python3-bottle uwsgi-plugin-python3 bc unrar
RUN rm -f /var/cache/apt/archives/*.deb /var/lib/apt/lists/*.deb

RUN mkdir /code
ADD . /code/

WORKDIR /code

CMD [ "uwsgi", "--socket", "0.0.0.0:8080", "--uid", "nobody", "--plugins", "python3", "--protocol", "http", "--processes", "4", "--wsgi", "server:app" ]

EXPOSE 8080
