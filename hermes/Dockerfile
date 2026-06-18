FROM nousresearch/hermes-agent:v2026.6.5

RUN apt-get update \
    && apt-get install -y --no-install-recommends jq haproxy \
    && rm -rf /var/lib/apt/lists/*

COPY --chown=root:root --chmod=0755 rootfs/etc/cont-init.d/00-read-config /etc/cont-init.d/00-read-config
COPY --chown=root:root --chmod=0755 rootfs/etc/services.d/haproxy/run /etc/services.d/haproxy/run

CMD ["gateway", "run"]
