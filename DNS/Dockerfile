FROM ubuntu:latest

RUN apt-get update && apt-get upgrade install -y bind9 bind9utils dnsutils bind9

# Copy config files
COPY parnamirim.ifrn.asa.br /etc/bind 
COPY ifrn.asa.br /etc/bind
COPY named.conf.local /etc/bind 

# Expose Ports
EXPOSE 53/tcp
EXPOSE 53/udp
EXPOSE 443/tcp


# Start the Name Service
CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]
