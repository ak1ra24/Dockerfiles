FROM ubuntu:18.10

RUN apt update \
 && apt install -y unbound
RUN mkdir -p /etc/unbound
COPY unbound.conf /etc/unbound/unbound.conf
CMD ["unbound", "-d", "-c", "/etc/unbound/unbound.conf"]
EXPOSE 53
