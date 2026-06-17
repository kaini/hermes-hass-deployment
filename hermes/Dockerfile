FROM nousresearch/hermes-agent:v2026.6.5

RUN apt-get update \
    && apt-get install -y --no-install-recommends jq \
    && rm -rf /var/lib/apt/lists/*

ADD rootfs/etc/cont-init.d/00-read-config /etc/cont-init.d/00-read-config

CMD ["gateway", "run"]
