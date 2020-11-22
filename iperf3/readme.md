[![Docker Stars](https://img.shields.io/docker/stars/bingo592/iperf3.svg)](https://hub.docker.com/r/bingo592/iperf3/) [![Docker Pulls](https://img.shields.io/docker/pulls/bingo592/iperf3.svg)](https://hub.docker.com/r/bingo592/iperf3/)

[TOC]
- [docker: iperf3](#docker--iperf3)
  * [Feature](#feature)
    + [Supported tags and respective `Dockerfile` links](#supported-tags-and-respective--dockerfile--links)
    + [Reference](#reference)
  * [Prepare the host](#prepare-the-host)
    + [Pulling from Docker hub](#pulling-from-docker-hub)
    + [Running the image](#running-the-image)
    + [Test with the server](#test-with-the-server)
  * [Thanks](#thanks)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>
# docker: iperf3

This is a Docker image to run the [iperf3](https://github.com/esnet/iperf) commandline tool in server mode.
iPerf3 (iPerf v3) is a tool for active measurements of the maximum achievable bandwidth on IP networks.
It supports tuning of various parameters related to timing, buffers and protocols (TCP, UDP, with IPv4 and IPv6).
For each test it reports the bandwidth, loss, and other parameters.

________________________________________
- Test TCP

```sh
C:\Users\Example>iperf3 -c speedtest.mydomain.local
Connecting to host speedtest.mydomain.local, port 5201
[  4] local 192.168.1.100 port 53917 connected to 192.168.1.50 port 5201
[ ID] Interval           Transfer     Bandwidth
[  4]   0.00-1.00   sec   112 MBytes   941 Mbits/sec
[  4]   1.00-2.00   sec   112 MBytes   942 Mbits/sec
[  4]   2.00-3.00   sec   112 MBytes   942 Mbits/sec
[  4]   3.00-4.00   sec   112 MBytes   943 Mbits/sec
[  4]   4.00-5.00   sec   112 MBytes   941 Mbits/sec
[  4]   5.00-6.00   sec   112 MBytes   942 Mbits/sec
[  4]   6.00-7.00   sec   112 MBytes   942 Mbits/sec
[  4]   7.00-8.00   sec   112 MBytes   942 Mbits/sec
[  4]   8.00-9.00   sec   112 MBytes   942 Mbits/sec
[  4]   9.00-10.00  sec   112 MBytes   942 Mbits/sec
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bandwidth
[  4]   0.00-10.00  sec  1.10 GBytes   942 Mbits/sec                  sender
[  4]   0.00-10.00  sec  1.10 GBytes   942 Mbits/sec                  receiver

iperf Done.
```
________________________________________
- Test UDP

```sh
C:\Users\Example>iperf3 -R -O 1 -u -b 50M -c speedtest.mydomain.local
Connecting to host speedtest.mydomain.local, port 5201
[  4] local 192.168.1.100 port 60469 connected to 192.168.1.50 port 5201
Reverse mode, remote host speedtest.mydomain.local is sending
[  4]   0.00-1.00   sec  6.17 MBytes  51.7 Mbits/sec  0.034 ms  23/813 (2.8%)  (omitted)
[  4]   0.00-1.00   sec  5.97 MBytes  50.0 Mbits/sec  0.028 ms  0/764 (0%)
[  4]   1.00-2.00   sec  5.96 MBytes  50.0 Mbits/sec  0.018 ms  0/763 (0%)
[  4]   2.00-3.00   sec  5.96 MBytes  50.0 Mbits/sec  0.016 ms  0/763 (0%)
[  4]   3.00-4.00   sec  5.96 MBytes  50.0 Mbits/sec  0.018 ms  0/763 (0%)
[  4]   4.00-5.00   sec  5.96 MBytes  50.0 Mbits/sec  0.014 ms  0/763 (0%)
[  4]   5.00-6.00   sec  5.96 MBytes  50.0 Mbits/sec  0.010 ms  0/763 (0%)
[  4]   6.00-7.00   sec  5.95 MBytes  50.0 Mbits/sec  0.015 ms  0/762 (0%)
[  4]   7.00-8.00   sec  5.96 MBytes  50.0 Mbits/sec  0.015 ms  0/763 (0%)
[  4]   8.00-9.00   sec  5.96 MBytes  50.0 Mbits/sec  0.023 ms  0/763 (0%)
[  4]   9.00-10.00  sec  5.95 MBytes  50.1 Mbits/sec  0.011 ms  0/762 (0%)
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bandwidth       Jitter    Lost/Total Datagrams
[  4]   0.00-10.00  sec  60.0 MBytes  50.3 Mbits/sec  0.011 ms  0/7629 (0%)
[  4] Sent 7629 datagrams

iperf Done.
```
________________________________________
## Feature
### Supported tags and respective `Dockerfile` links

- `latest` [*(Dockerfile)*](https://github.com/Liaozhebin/docker/blob/main/iperf3/Dockerfile.architecture)

### Reference
- Supported architectures ([*more info*](https://github.com/docker-library/official-images#architectures-other-than-amd64)):  `amd64`,  `arm32v6` , `arm32v7` , `arm64v8` , `i386` , `ppc64le` , `s390x`

- Runs as non-root user
- Small image size
- Small number of layers
- Supports TCP and UDP

Total size of this image is only:

[![](https://images.microbadger.com/badges/image/bingo592/iperf3.svg)](https://microbadger.com/images/bingo592/iperf3)

________________________________________
## Prepare the host

Docker images are built for quick deployment in various computing cloud providers. For more information on docker and containerization technologies, refer to [official document](https://docs.docker.com/).

If you need to install docker by yourself, follow the [official installation guide](https://docs.docker.com/install/).

### Pulling from Docker hub
If you want to obtain the image from Docker registry, you can use the following command:
```sh
docker pull bingo592/iperf3
```
This pulls the latest release of KMS Server. It can be found at [Docker Hub](https://hub.docker.com/repository/docker/bingo592/iperf3).
________________________________________
### Running the image
In order to run the iperf server, use the following:
```sh
docker run --restart=unless-stopped --name=iperf3_server -d -p 5201:5201/tcp -p 5201:5201/udp bingo592/iperf3
```
At that point, you can use your Docker server as an iperf3 server to begin testing your network.

**Note:** The TCP/UDP port number 1688 must be opened in firewall.
### Test with the server
In order to test the iperf server, use the following:
```sh
C:\Users\example> iperf3.exe -c ${your_server_ip} -t ${test_time_seconds}
C:\Users\example> iperf3.exe -c 127.0.0.1 -t 5   # Test the server tcp with 5 seconds by Windows (Default testing client upload bandwidth) 
docker run -it --rm bingo592/iperf3 -c 127.0.0.1 -t 5 -R  # Test the server tcp with 5 seconds by docker (With parameter -R to test client download bandwidth) 
```

## Thanks
-  [使用 Docker Buildx 构建多种系统架构镜像](https://teddysun.com/581.html)
-  [A iperf3 project of docker on amd64](https://hub.docker.com/r/mlabbe/iperf3) 
