FROM ubuntu:18.10

RUN apt-get update && apt-get install -y kea-dhcp4-server kea-admin mysql-client
RUN mkdir -p /etc/kea/
COPY kea-config.json /etc/kea/kea-config.json

RUN mkdir -p /var/run/kea/
RUN touch /var/run/kea/isc_kea_logger_lockfile

RUN mkdir -p /usr/local/bin/
COPY startup.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/startup.sh
CMD ["/usr/local/bin/startup.sh"]
# ENTRYPOINT ["kea-dhcp4"]
# CMD ["-c", "/etc/kea/kea-config.json"]
# EXPOSE 67
