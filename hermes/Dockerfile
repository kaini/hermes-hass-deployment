FROM nousresearch/hermes-agent@sha256:e93a26adae343f0a56b80e84c13d965d6cc54e368d10f3ef62d21cc591787c1e

RUN apt-get update \
    && apt-get install -y --no-install-recommends jq haproxy python3-requests \
    && rm -rf /var/lib/apt/lists/*

COPY --chown=root:root --chmod=0755 rootfs/etc/cont-init.d/00-read-config /etc/cont-init.d/00-read-config
COPY --chown=root:root --chmod=0644 rootfs/etc/s6-overlay/s6-rc.d/haproxy/dependencies.d/base /etc/s6-overlay/s6-rc.d/haproxy/dependencies.d/base
COPY --chown=root:root --chmod=0755 rootfs/etc/s6-overlay/s6-rc.d/haproxy/run /etc/s6-overlay/s6-rc.d/haproxy/run
COPY --chown=root:root --chmod=0644 rootfs/etc/s6-overlay/s6-rc.d/haproxy/type /etc/s6-overlay/s6-rc.d/haproxy/type
COPY --chown=root:root --chmod=0644 rootfs/etc/s6-overlay/s6-rc.d/user/contents.d/haproxy /etc/s6-overlay/s6-rc.d/user/contents.d/haproxy

CMD ["gateway", "run"]
