# course_netdata


Net Data







```
version: '3'
services:
  netdata:
    image: netdata/netdata
    container_name: netdata
    hostname: example.com # set to fqdn of host
    ports:
    - 19999:19999
    restart: unless-stopped
    cap_add:
    - SYS_PTRACE
    security_opt:
    - apparmor:unconfined
    volumes:
      - netdataconfig:/etc/netdata
      - netdatalib:/var/lib/netdata
      - netdatacache:/var/cache/netdata
      - /etc/passwd:/host/etc/passwd:ro
      - /etc/group:/host/etc/group:ro
      - /proc:/host/proc:ro
      - /sys:/host/sys:ro
      - /etc/os-release:/host/etc/os-release:ro
volumes:
  netdataconfig:
  netdatalib:
  netdatacache:
 ```
  
  
