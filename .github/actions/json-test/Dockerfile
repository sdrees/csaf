FROM debian:stable
LABEL description="Debian-based python container for CSAF development work"

# keeps down noise by telling apt that this shell is not interactive
ARG DEBIAN_FRONTEND="noninteractive"

# update packages
#RUN apt-get update -q && apt-get upgrade -y --no-install-recommends -q

# install all necessary software components
RUN apt-get update -q \
 && apt-get install -y --no-install-recommends -qq \
    git \
    python3 \
    python3-simplejson \
    python3-jsonpath-rw \
    python3-pip \
    python3-setuptools \
    python3-wheel

RUN pip3 install --upgrade pip \
 && pip3 install git+https://github.com/anexia-it/jsonschema@draft2020-12#egg=jsonschema[format]

COPY entrypoint.sh /

ENTRYPOINT ["/entrypoint.sh"]
