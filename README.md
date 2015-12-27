# DockerflixDNS
Dockerflix's complementary DNS service implementation thru dnsmasq

[Dockerflix](https://github.com/trick77/dockerflix) requires a DNS spoofing service to work, this is a docker implementation of such DNS service so people can use services outside the US simply by modifying their DNS address.

## Usage

Create a docker image:
`docker build -t hbjcr/dockerflixdns .`

Create a new DockerflixDNS container:
`docker run -d -p 53:53/udp hbjcr/dockerflixdns`

Modify your dnsmasq.conf file to include the domain entries required by Dockerflix:
`Instructions`

Restart your DockerflixDNS container:
`Instructions`

Modify your init routine to start your container after rebooting:
`Instuctions`

## Test

Run the following command from your host server:
`dig @localhost amazon.com`

The IP number you added to your dnsmasq.conf file should be listed
