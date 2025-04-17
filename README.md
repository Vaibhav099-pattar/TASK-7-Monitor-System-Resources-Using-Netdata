# TASK-7-Monitor-System-Resources-Using-Netdata
Tools Required:
a.Docker
b.Netdata 
Steps
1.Run Netdata using Docker
i.e -> docker run -d --name=netdata \
  -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  -v netdataconfig:/etc/netdata \
  -v netdatalib:/var/lib/netdata \
  -v netdatacache:/var/cache/netdata \
  -v /etc/passwd:/host/etc/passwd:ro \
  -v /etc/group:/host/etc/group:ro \
  -v /proc:/host/proc:ro \
  -v /sys:/host/sys:ro \
  -v /etc/os-release:/host/etc/os-release:ro \
  netdata/netdata
2.Open the Dashboard ->  http://localhost:19999
3.docker exec -it netdata cat /var/log/netdata/error.log





  



