# Rancher 1 Hetzner Cloud UI Driver

[![Build Status](https://travis-ci.org/mxschmitt/ui-driver-hetzner.svg?branch=v1.6)](https://travis-ci.org/mxschmitt/ui-driver-hetzner)

Rancher UI driver for the [Hetzner Cloud](hetzner.de/cloud)

## Using

* Add a Machine Driver in Rancher (Admin tab -> Settings -> Machine Drivers)
  * Download URL: `https://github.com/JonasProgrammer/docker-machine-driver-hetzner/releases/download/1.1.0/docker-machine-driver-hetzner_1.1.0_linux_amd64.tar.gz`
  * Custom UI URL: `https://storage.googleapis.com/hcloud-rancher-v1-ui-driver/component.js`
* Wait for the driver to become "Active"
* Go to Infrastructure -> Hosts -> Add Host, your driver and custom UI should show up.

![Authentication screen](docs/authentication-screen.png)
![Configuration screen](docs/configuration-screen.png)

## Development

This package contains a small web-server that will serve up the custom driver UI at `http://localhost:3000/component.js`.  You can run this while developing and point the Rancher settings there.
* `npm start`
* The driver name can be optionally overridden: `npm start -- --name=DRIVERNAME`
* The compiled files are viewable at http://localhost:3000.
* **Note:** The development server does not currently automatically restart when files are changed.

## Building

For other users to see your driver, you need to build it and host the output on a server accessible from their browsers.

* `npm install`
* `npm build`
* Copy the contents of the `dist` directory onto a webserver.
  * If your Rancher is configured to use HA or SSL, the server must also be available via HTTPS.
