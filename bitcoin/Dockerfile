FROM python:3.6

# Set up code directory
# RUN mkdir -p /usr/src/app
WORKDIR /src

# Install Linux dependencies
RUN apt-get update && apt-get install -y libssl-dev wget \
  && apt install -y netcat-openbsd \
  && git clone https://github.com/vagabondan/docker-python.git \
  && cd docker-python \
  && pwd \
  && git status \
  && git checkout remotes/origin/bitcoin \
  && git status \
  && cd .. \
  && cat docker-python/bitcoin/requirements.txt \
  && pip install -r docker-python/bitcoin/requirements.txt \
  && pip install -e . 

WORKDIR /app
