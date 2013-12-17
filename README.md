# Project Status Update

The project is still in development but due to current pending legal issues those changes are not being pushed to this repository as-is. Instead, we will be pushing a complete replacement to this repository. At some point in the future, anyone who has cloned this repository may find it has been replaced by a forced push and you will have to re-clone to get any updates. We might set up a temporary repository for active development which we’ll then push over the top of the official one.

Details about ongoing legal issues can be found here: http://southforksecurity.com/litigation.html.

Thanks to everyone for their support. Leve Visdom! Skål!

# Mimir 
Mimir is a network traffic flow analysis backend for Visdom. It is currently under heavy development and the Dev branch will be the default while master exists as a "stable" branch as much as possible during early development processes.

Mimir requires the GoAVL library available at http://code.google.com/p/go-avltree/

To build the entire tree run 'go build' from the home directory.

Mimir uses Visdom for a frontend: http://github.com/visdom/visdom

## Quickstart Guide

### Install dependencies

Mimir depends on libgeoip and libpcap for sniffing and geolocating network traffic.

Ubuntu Example:

```shell
apt-get install git golang libgeoip-dev libpcap-dev
```
### Download and compile

```shell
git clone https://github.com/visdom/visdom.git
cd visdom
GOPATH=$PWD go get github.com/visdom/mimir
wget http://geolite.maxmind.com/download/geoip/database/GeoLiteCity.dat.gz
gunzip GeoLiteCity.dat.gz
sudo ./bin/mimir -web-enable -d eth0 -web-port 8080 -web-root ./ -maxmind-db ./GeoLiteCity.dat
```

Browse to http://your.host.here:8080

## Copyright and License
Copyright 2013 Southfork Security, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
