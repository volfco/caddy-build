# borrowed from https://github.com/open-telemetry/opentelemetry-collector-releases/blob/main/distributions/otelcol-contrib/Dockerfile
FROM debian:latest

# otelcol or otelcol-contrib
ARG OTEL_TYPE="otelcol-contrib"
ARG OTEL_VERSION=0.89.0

RUN apt-get update -qq && \
    apt-get install -y --no-install-recommends \
        systemd curl \
    && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    # Set systemctl to not be executable- so the postinstall script doesn't fail
    chmod -x /usr/bin/systemctl && \
    curl -L -o /tmp/otel_tmp.dpkg https://github.com/open-telemetry/opentelemetry-collector-releases/releases/download/v${OTEL_VERSION}/${OTEL_TYPE}_${OTEL_VERSION}_linux_${BUILDARCH}.deb && \
    dpkg -i /tmp/otel_tmp.dpkg && \
    rm /tmp/otel_tmp.dpkg

ENTRYPOINT ["/usr/bin/otelcol-contrib"]
CMD ["--config", "/etc/otelcol-contrib/config.yaml"]
EXPOSE 4317 55678 55679