# vagrant-prometheus-mysql-docker-standalone

~~~~

vagrant up vg-pro-gr-lk-03 (remote docker engine first)
vagrant up vg-pro-gr-lk-02


vagrant@vg-pro-gr-lk-02:~$ docker ps
CONTAINER ID   IMAGE                         COMMAND                  CREATED              STATUS              PORTS                                                    NAMES
39fe98ed0a88   grafana/grafana               "/run.sh"                About a minute ago   Up About a minute   0.0.0.0:3000->3000/tcp, :::3000->3000/tcp                grafana-server
c03bdc07c738   prom/prometheus               "/bin/prometheus --c…"   2 minutes ago        Up 2 minutes        0.0.0.0:9090->9090/tcp, :::9090->9090/tcp                prometheus-server
91dbfcf12ca2   prom/mysqld-exporter:latest   "/bin/mysqld_exporte…"   2 minutes ago        Up 2 minutes        0.0.0.0:49157->9104/tcp, :::49157->9104/tcp              mysql57-exporter
ff0db25ae753   prom/mysqld-exporter:latest   "/bin/mysqld_exporte…"   2 minutes ago        Up 2 minutes        0.0.0.0:49156->9104/tcp, :::49156->9104/tcp              mysql80-exporter
bb15f8e32646   mysql:5.7                     "docker-entrypoint.s…"   2 minutes ago        Up 2 minutes        33060/tcp, 0.0.0.0:49155->3306/tcp, :::49155->3306/tcp   mysql57
ac25c8e47ccc   mysql:8                       "docker-entrypoint.s…"   3 minutes ago        Up 2 minutes        33060/tcp, 0.0.0.0:49154->3306/tcp, :::49154->3306/tcp   mysql80


Prometheus GUI
http://192.168.53.9:9090/ 
Grafana (admin/admin)
http://192.168.53.9:3000

Local Docker Engine metrics
http://192.168.53.9:9323/metrics
Remote  Docker Engine metrics
http://192.168.53.10:9323/metrics
Mysql metrics
http://mysql57-exporter:9104/metrics
http://mysql80-exporter:9104/metrics
Prometheus
http://c03bdc07c738:9090/metrics


Grafana GUI
Add Source - Prometheus
http://192.168.53.9:9090
~~~~