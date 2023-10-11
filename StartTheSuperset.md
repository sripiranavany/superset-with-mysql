## if low memory issue

- start with out superset-worker and superset-worker-beat then after success fully start of the superset then start both

* docker-compose -f docker-compose-non-dev.yml up superset-worker superset-worker-beat

- to connect the mysql

* both superset related services and mysql need to be in same docker network -> then we can use the docker gateway ip as the mysql ip in the superset mysql connection process

* docker inspect <mysql-container-id> | grep "Gateway"

* for drill : drill+sadrill://user:password@localhost:8047/dfs?use_ssl=False
