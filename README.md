# DockerflixDNS
[![](https://badge.imagelayers.io/hbjcr/dockerflixdns:latest.svg)](https://imagelayers.io/?images=hbjcr/dockerflixdns:latest 'Get your own badge on imagelayers.io')

Dockerflix's complementary DNS service implementation thru dnsmasq

[Dockerflix](https://github.com/trick77/dockerflix) requires a DNS spoofing service to work, this is a docker implementation of such DNS service so people can use services outside the US simply by modifying their DNS address.

An official docker image can be found here: https://hub.docker.com/r/hbjcr/dockerflixdns/

## Usage

Create a docker image:

```docker pull hbjcr/dockerflixdns```

Create a new DockerflixDNS container:

```docker run -d -p 53:53/udp hbjcr/dockerflixdns```

Find the location of your configuration file:

```docker inspect <containerID>```

Modify your dnsmasq.conf file to include the domain entries required by Dockerflix (read the instructions on how to use gendns-conf.py first):

```vim /var/lib/docker/volumes/.../_data/dnsmasq.conf```

Restart your DockerflixDNS container:

```docker restart <containerID>```

## Test

Run the following command from your host server:

```dig @localhost amazon.com```

The IP number you added to your dnsmasq.conf file should be listed
