<img width="1260" alt="Screenshot 2022-12-30 at 5 46 37 PM" src="https://user-images.githubusercontent.com/43849911/210069351-88c7500a-a3e6-4c3c-84c3-ea6c2e71cf54.png">
<img width="1261" alt="Screenshot 2022-12-30 at 5 57 51 PM" src="https://user-images.githubusercontent.com/43849911/210070184-e30bff32-038e-47c1-815a-cc95310d663e.png">
<img width="1266" alt="Screenshot 2022-12-30 at 6 04 39 PM" src="https://user-images.githubusercontent.com/43849911/210070710-99b6727b-1a6d-42e2-9f38-f3c7ff16a8fa.png">
<img width="1039" alt="Screenshot 2022-12-31 at 1 42 36 AM" src="https://user-images.githubusercontent.com/43849911/210108579-0bb711a5-2969-46fb-af7e-5c9a5ff816f4.png">
<img width="617" alt="Screenshot 2022-12-31 at 1 43 11 AM" src="https://user-images.githubusercontent.com/43849911/210108613-b14d7914-e79c-4f52-8f4c-18e2dec7f4ca.png">
<img width="1161" alt="Screenshot 2022-12-31 at 1 44 37 AM" src="https://user-images.githubusercontent.com/43849911/210108704-be82030d-6c11-49b9-8376-ca27e5a4d694.png">
<img width="1743" alt="Screenshot 2022-12-31 at 1 48 27 AM" src="https://user-images.githubusercontent.com/43849911/210108964-f14d90d4-c6b4-48ed-a6ee-2a7be8595e3b.png">
<img width="1742" alt="Screenshot 2022-12-31 at 1 51 17 AM" src="https://user-images.githubusercontent.com/43849911/210109146-242e474b-0367-4d2b-bdc7-447e46345d2e.png">
<img width="955" alt="Screenshot 2022-12-31 at 1 58 53 AM" src="https://user-images.githubusercontent.com/43849911/210109585-da452744-f01c-4e84-80fa-78d6c24ec8b9.png">
<img width="1467" alt="Screenshot 2022-12-31 at 2 00 22 AM" src="https://user-images.githubusercontent.com/43849911/210109664-742f25a1-98c2-4db9-a757-f2c18b42e99d.png">

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
docker run -p 9090:9090 -v /Users/saiashish/Desktop/sai/projects/PrometheusAndGrafana/src/main/resources/prometheus.yml 
prom/prometheus

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

```
docker run -d --name=grafana88 -p 3000:3000 grafana/grafana
Unable to find image 'grafana/grafana:latest' locally
latest: Pulling from grafana/grafana
9621f1afde84: Pull complete 
db7fbc631880: Pull complete 
afb29f8d05c6: Pull complete 
2d9c2cfef851: Pull complete 
0f9c8679de96: Pull complete 
d8d1a816d728: Pull complete 
09aac180a7fc: Pull complete 
1c5ec5c4e84a: Pull complete 
0b0714ac27d7: Pull complete 
Digest: sha256:2a73ae33c9f0c51af6eced2ef185d5d3682b4c378c4fdd6941a14e8ea4a3e95b
Status: Downloaded newer image for grafana/grafana:latest
81e3c926a838c78a6e45a05e750e960f261dea0b5bc5de5f081718d4fe5be7e6
```

