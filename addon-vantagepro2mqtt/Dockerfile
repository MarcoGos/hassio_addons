ARG BUILD_FROM
FROM $BUILD_FROM

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN \
  apk add --no-cache \
    python3 \
    py3-pip \
  && pip3 install PyVantagePro-MarcoGos --break-system-packages \
  && pip3 install paho-mqtt --break-system-packages \
  && pip3 install colorlog --break-system-packages

COPY rootfs /

WORKDIR /

# Copy data for add-on
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
