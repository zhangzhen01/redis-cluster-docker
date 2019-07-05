# redis-cluster-docker
create redis cluster with docker-compose

第一步，启动镜像 docker-compose up -d

第二步，生成集群：docker run --rm -it inem0o/redis-trib create --replicas 1 172.31.32.13:8001 172.31.32.13:8002 172.31.32.13:8003 172.31.32.13:8004 172.31.32.13:8005 172.31.32.13:8006
将该命令ip改为宿主机ip

第三步，登录镜像，连接查看集群状态：
docker exec -it containerId bash
redis-cli -c -p 8004
172.31.32.13-redis-cluster:0>cluster info
cluster_state:ok
cluster_slots_assigned:16384
cluster_slots_ok:16384
cluster_slots_pfail:0
cluster_slots_fail:0
cluster_known_nodes:6
cluster_size:3
cluster_current_epoch:6

大功告成！
