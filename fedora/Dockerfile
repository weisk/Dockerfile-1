FROM fedora

LABEL org.label-schema.schema-version="Fedora 30 (Container Image)" \
    org.label-schema.name="fedora Base Image" \
    maintainer="anish2good@yahoo.co.in" \
    org.label-schema.vcs-description="Fedora 30 (Container Image)" \
    org.label-schema.docker.cmd="docker run 0cloud0/playground:fedora " \
    org.label-schema.vendor="CentOS" \
    org.label-schema.license="GPLv2" \
    org.label-schema.build-date="20190801"

RUN echo "**** install Python ****" && \
    dnf -y install python36 findutils && \
    if [ ! -e /usr/bin/python ]; then ln -sf python3 /usr/bin/python ; fi && \
    \
    echo "**** install pip ****" && \
    /usr/bin/python3 -m ensurepip && \
    pip3 install --no-cache --upgrade pip setuptools wheel && \
    if [ ! -e /usr/bin/pip ]; then ln -s pip3 /usr/bin/pip ; fi && \
    pip install pyxtermjs flask_cors

COPY . ./usr/local/lib/python3.7/site-packages/pyxtermjs/