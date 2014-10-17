Routing release
===============

The BOSH release that changes the route table and the default gateway.
Changes to the routing table will be made when `routing` job starts/stops.

Only tested with Ubuntu Trusty.

Usage
-----

To customize routing on the machine collocate `routing` release job
and specify routing properties.

For example to add extra route entries to the CF router VM:

```
jobs:
...
- name: router
  instances: 2
  templates:
  - {name: gorouter, release: cf}
  - {name: routing, release: routing}
  networks: [...]
  properties:
    ...
    routing:
      default_gw: 123.456.194.254
      routes:
      - subnet: 123.456.0.0
        netmask: 255.192.0.0
        gateway: 123.424.235.254
```

Todo
----

* Properly remove routing entries when job is stopped
