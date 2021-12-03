FROM ghcr.io/zerotens/base:latest

COPY openvpn.sh /usr/bin/

# Install openvpn
RUN apk --no-cache --no-progress add bash curl ip6tables iptables openvpn shadow tini tzdata && \
    addgroup -S vpn && \
    chmod +x /usr/bin/openvpn.sh && \
    rm -rf /tmp/*

VOLUME ["/vpn"]

ENTRYPOINT ["/sbin/tini", "--", "/usr/bin/openvpn.sh"]