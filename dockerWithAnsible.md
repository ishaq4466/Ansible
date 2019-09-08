
```
docker create --name=manager -it smartbuddy/ansible-centos7:manager #creating a container
docker create --name=node1 -it smartbuddy/ansible-centos7:node #creating a container
docker create --name=node2 -it smartbuddy/ansible-centos7:node #creating a container
docker start manager
docker start node2
docker start node1

docker run -idt -v /sys/fs/cgroup:/sys/fs/cgroup:ro --cap-add SYS_ADMIN --name manager smartbuddy/ansible-centos7:manager

docker run -idt -v /sys/fs/cgroup:/sys/fs/cgroup:ro --cap-add SYS_ADMIN --name node1 smartbuddy/ansible-centos7:node

docker run -idt -v /sys/fs/cgroup:/sys/fs/cgroup:ro --cap-add SYS_ADMIN --name node2 smartbuddy/ansible-centos7:node

docker exec -it --user ansible manager /bin/bash
docker exec -it --user ansible node1 /bin/bash
docker exec -it --user ansible node2 /bin/bash

```


