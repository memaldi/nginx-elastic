FROM logstash

COPY logstash.conf /logstash/config-dir/

VOLUME /var/log/nginx

CMD ["-f", "/logstash/config-dir/logstash.conf"]
