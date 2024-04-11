ARG caddy_version=latest
FROM docker.io/caddy:${caddy_version}-builder as build
RUN xcaddy build \
    --with github.com/caddy-dns/namecheap \
    --with github.com/mholt/caddy-l4/layer4 \
    --with github.com/caddy-dns/vultr \
    --with github.com/caddy-dns/vercel \
    --with github.com/caddy-dns/tencentcloud \
    --with github.com/caddy-dns/route53 \
    --with github.com/caddy-dns/rfc2136 \
    --with github.com/caddy-dns/powerdns \
    --with github.com/caddy-dns/ovh \
    --with github.com/caddy-dns/openstack-designate \
    --with github.com/caddy-dns/njalla \
    --with github.com/caddy-dns/metaname \
    --with github.com/caddy-dns/mailinabox \
    --with github.com/caddy-dns/linode \
    --with github.com/caddy-dns/leaseweb \
    --with github.com/caddy-dns/hexonet \
    --with github.com/caddy-dns/hetzner \
    --with github.com/caddy-dns/googleclouddns \
    --with github.com/caddy-dns/google-domains \
    --with github.com/caddy-dns/godaddy \
    --with github.com/caddy-dns/gandi \
    --with github.com/caddy-dns/duckdns \
    --with github.com/caddy-dns/dnspod \
    --with github.com/caddy-dns/dinahosting \
    --with github.com/caddy-dns/digitalocean \
    --with github.com/caddy-dns/ddnss \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/yroc92/postgres-storage \
    --with github.com/zhangjiayin/caddy-mysql-storage\
    --with github.com/mholt/caddy-dynamicdns

FROM docker.io/caddy:${caddy_version}
COPY --from=build /usr/bin/caddy /usr/bin/caddy
