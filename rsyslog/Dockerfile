FROM alpine:3.19

# Instala apenas o rsyslog sem dependências desnecessárias
RUN apk add --no-cache rsyslog

# Cria diretórios necessários
RUN mkdir -p /var/log/rsyslog /var/spool/rsyslog && \
    chown -R root:root /var/log/rsyslog

# Copia configuração
COPY rsyslog.conf /etc/rsyslog.conf

# Expõe portas
EXPOSE 514/udp

# Roda em foreground
CMD ["rsyslogd", "-n", "-f", "/etc/rsyslog.conf"]
