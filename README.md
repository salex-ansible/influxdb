Ansible InfluxDB role
=========

Simple role that installs InfluxDB on your server, copies config and creates basic admin user and database.

Requirements
------------

Ansible 2.0 and Ubuntu on the server.

Role Variables
--------------

InfluxDB package URL:

`influx_deb_url: 'https://dl.influxdata.com/influxdb/releases/influxdb_1.2.4_amd64.deb'`

Default Variables:

```
  influx:
    retention_enabled: true
    retention_interval: 30m
    shard_precreation_enabled: true
    shard_precreation_interval: 10m
    shard_precreation_period: 30m
    admin_enabled: true
    admin_address: ':8083'
    admin_https: false
    admin_auth: true
    admin_cert_path: "/etc/ssl/influxdb.pem"
    http_enabled: true
    http_address: ':8086'
    client_https_enabled: false
    client_cert_path: "/etc/ssl/influxdb.pem"
    udp_enabled: false
    udp_port: ':9001'
    database_name: 'superdb'
    admin_username: admin
    admin_password: admin

```

Dependencies
------------
No

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: alekseenkoss77.influxdb }

License
-------

BSD

