# Kong API Gateway

### Info
Kong API Gateway 0.8.3 with Rancher support. Using littlebaydigital/kong and PostgreSQL.

This service uses Rancher Meta Data service to work out the correct container IP address to add to the Kong cluster. And also
exposes necessary environment variables for easy connectivity with external Kong database.

### Config:

Once you select either PostgreSQL or Cassandra database backend, for `DB Hostname` you can either specify:

- PostgreSQL Host - either DNS record or a Rancher service in the format of `postgres-servicename.stackname`
- Cassandra Contact Points - in the format of `\"ip1:9046\",\"ip2:9046\"`, or a Rancher services in the format of `\"cassandra-servicename.stackname:9046\"`

### Database Requirements

PostgresSQL by default requires the specified database and username to already exist prior to service staring. Password is optional.

Cassandra by default does not require username nor password and it will automatically create the specified keyspace.

### Usage:
After the cluster spins up, you should be able to access:

- kong on port `8001`
- kong-dashboard on port `8080`
