FROM docker.cloudsmith.io/sturdy-waffle/build-images/image-build:latest

# Install App Repo
RUN curl -1sLf \
  "https://dl.cloudsmith.io/<TOKEN>/sturdy-waffle/app/cfg/setup/bash.deb.sh" \
  | bash

# Install sturdy-waffle
RUN apt-get update && apt-get install -y python3-sturdy-waffle gunicorn

RUN rm -rf /etc/apt/sources.list.d/*

ENTRYPOINT ["gunicorn", "-b", "0.0.0.0:5000", "sturdy_waffle:app"]
