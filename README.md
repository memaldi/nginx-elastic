# nginx-elastic

This is a docker-compose file to analyze logs from nginx with logstash, elasticsearch and kibana. Usage:

* Declare a new log format at nginx.conf for monitorizing the duration of each request:

```
log_format timed_combined '$remote_addr - $remote_user [$time_local] '
'"$request" $status $body_bytes_sent '
'"$http_referer" "$http_user_agent" '
'$request_time $upstream_response_time $pipe';

access_log /var/log/nginx/access.log timed_combined;
```
* Make logs readable for everyone:

```
$ sudo chmod a+r /var/log/nginx/access.log
```

* Launch the docker-compose script:

```
$ docker-compose up
```

Kibana is accessible at port `5601`.
