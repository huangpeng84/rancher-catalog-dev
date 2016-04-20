# Selenium Grid

This template creates a Selenium Grid with two nodes connected : a Firefox and a Chrome.

## Usage

Choose the Selenium's port you want to expose (in order to connect from remote locations) and the domain used by [Traefik](http://traefik.github.io).

Console will be accessible at [selenium.${DOMAIN}/grid/console](http://selenium.localhost)/grid/console

Hub will be accessible at [docker_host_ip_or_${DOMAIN}:${SELENIUM_PORT}/wd/hub](http://docker_host_ip_or_localhost):${SELENIUM_PORT}/wd/hub

You can scale up Firefox ou Chrome service to add node to the grid.
