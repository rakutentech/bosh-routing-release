Routing release
===================

This bosh release is a small release which apply a shell script during the start / stop of monit
The shell script will change the route table and the default gateway as requested.


Only tested with ubuntu.




Properties
-------------


```
//You can co-locate this template
- name: routing
  release: routing
- name: gorouter


- name: router
  instances: 2
  networks:
  ...
  properties:
    ...
    routing:
      default_gw: 123.456.194.254
      routes:
      - subnet: 123.456.0.0
        netmask: 255.192.0.0
        gateway: 123.424.235.254
templates: //You can co-locate this template
- name: routing
  release: routing
- name: gorouter
...   

```

TODO
-------------

A lot of todo, more than I can write ....

