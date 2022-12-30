<img width="1260" alt="Screenshot 2022-12-30 at 5 46 37 PM" src="https://user-images.githubusercontent.com/43849911/210069351-88c7500a-a3e6-4c3c-84c3-ea6c2e71cf54.png">
<img width="1261" alt="Screenshot 2022-12-30 at 5 57 51 PM" src="https://user-images.githubusercontent.com/43849911/210070184-e30bff32-038e-47c1-815a-cc95310d663e.png">
<img width="1266" alt="Screenshot 2022-12-30 at 6 04 39 PM" src="https://user-images.githubusercontent.com/43849911/210070710-99b6727b-1a6d-42e2-9f38-f3c7ff16a8fa.png">

https://hub.docker.com/r/prom/prometheus

```
open -a Docker
docker pull prom/prometheus
```

```
docker image ls
REPOSITORY        TAG       IMAGE ID       CREATED       SIZE
prom/prometheus   latest    932c2dbe7d3e   10 days ago   231MB
```

```
ifconfig | grep "inet " | grep -Fv 127.0.0.1 | awk '{print $2}'

192.168.29.46
```

```
docker run -p 9090:9090 -v /Users/saiashish/Desktop/sai/projects/PrometheusAndGrafana/src/main/resources/prometheus.yml prom/prometheus

ts=2022-12-30T20:05:54.696Z caller=main.go:512 level=info msg="No time or size retention was set so using the default time retention" duration=15d
ts=2022-12-30T20:05:54.696Z caller=main.go:556 level=info msg="Starting Prometheus Server" mode=server version="(version=2.41.0, branch=HEAD, revision=c0d8a56c69014279464c0e15d8bfb0e153af0dab)"
ts=2022-12-30T20:05:54.696Z caller=main.go:561 level=info build_context="(go=go1.19.4, platform=linux/amd64, user=root@d20a03e77067, date=20221220-10:40:45)"
ts=2022-12-30T20:05:54.696Z caller=main.go:562 level=info host_details="(Linux 5.15.49-linuxkit #1 SMP Tue Sep 13 07:51:46 UTC 2022 x86_64 927340a5ae8c (none))"
ts=2022-12-30T20:05:54.696Z caller=main.go:563 level=info fd_limits="(soft=1048576, hard=1048576)"
ts=2022-12-30T20:05:54.696Z caller=main.go:564 level=info vm_limits="(soft=unlimited, hard=unlimited)"
ts=2022-12-30T20:05:54.697Z caller=web.go:559 level=info component=web msg="Start listening for connections" address=0.0.0.0:9090
ts=2022-12-30T20:05:54.698Z caller=main.go:993 level=info msg="Starting TSDB ..."
ts=2022-12-30T20:05:54.700Z caller=tls_config.go:232 level=info component=web msg="Listening on" address=[::]:9090
ts=2022-12-30T20:05:54.700Z caller=tls_config.go:235 level=info component=web msg="TLS is disabled." http2=false address=[::]:9090
ts=2022-12-30T20:05:54.703Z caller=head.go:562 level=info component=tsdb msg="Replaying on-disk memory mappable chunks if any"
ts=2022-12-30T20:05:54.703Z caller=head.go:606 level=info component=tsdb msg="On-disk memory mappable chunks replay completed" duration=5.558µs
ts=2022-12-30T20:05:54.703Z caller=head.go:612 level=info component=tsdb msg="Replaying WAL, this may take a while"
ts=2022-12-30T20:05:54.703Z caller=head.go:683 level=info component=tsdb msg="WAL segment loaded" segment=0 maxSegment=0
ts=2022-12-30T20:05:54.703Z caller=head.go:720 level=info component=tsdb msg="WAL replay completed" checkpoint_replay_duration=26.017µs wal_replay_duration=391.412µs wbl_replay_duration=114ns total_replay_duration=439.816µs
ts=2022-12-30T20:05:54.704Z caller=main.go:1014 level=info fs_type=EXT4_SUPER_MAGIC
ts=2022-12-30T20:05:54.704Z caller=main.go:1017 level=info msg="TSDB started"
ts=2022-12-30T20:05:54.704Z caller=main.go:1197 level=info msg="Loading configuration file" filename=/etc/prometheus/prometheus.yml
ts=2022-12-30T20:05:54.705Z caller=main.go:1234 level=info msg="Completed loading of configuration file" filename=/etc/prometheus/prometheus.yml totalDuration=513.823µs db_storage=949ns remote_storage=1.536µs web_handler=376ns query_engine=711ns scrape=245.307µs scrape_sd=14.982µs notify=19.121µs notify_sd=7.367µs rules=1.234µs tracing=3.992µs
ts=2022-12-30T20:05:54.705Z caller=main.go:978 level=info msg="Server is ready to receive web requests."
ts=2022-12-30T20:05:54.705Z caller=manager.go:953 level=info component="rule manager" msg="Starting rule manager..."
```
