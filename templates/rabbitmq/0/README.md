# Rabbit MQ

This template creates a RabbitMQ instance with web management UI.

## Usage

Choose the RabbitMQ's port you want to expose (in order to connect from remote locations) and the domain used by [Traefik](http://traefik.github.io).

Console will be accessible at [rabbit.${DOMAIN}](http://rabbit.localhost) with default credentials (`guest`@`guest`)

Maximum memory is set to 450MB and the default virtual host is `rabbit`.