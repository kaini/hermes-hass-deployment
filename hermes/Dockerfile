FROM nousresearch/hermes-agent:v2026.6.5
USER root

ADD rootfs/etc/cont-init.d/01-read-config /etc/cont-init.d/01-read-config

USER hermes
CMD ["gateway", "run"]
ENTRYPOINT []
