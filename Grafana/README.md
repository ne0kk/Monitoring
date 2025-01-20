Использовал этотй гайд в качестве примера. 

https://www.dmosk.ru/miniinstruktions.php?mini=prometheus-stack-docker


![image](https://github.com/user-attachments/assets/d6db79e9-5370-4305-b60d-06bdf9520edb)
![image](https://github.com/user-attachments/assets/ef33daf8-3327-4afe-a9c4-7350df1a2500)
![image](https://github.com/user-attachments/assets/0faf0717-5511-4ec6-951b-c128275c1c42)

Вводим идентификатор дашборда. Для Node Exporter это 1860:
![image](https://github.com/user-attachments/assets/fcd6b126-a2a0-4414-8d01-add0116a81bb)

![image](https://github.com/user-attachments/assets/a7403e4e-4796-4a50-86d9-fb500f4070aa)
![image](https://github.com/user-attachments/assets/0ecb3917-24af-4e5a-92b9-07283ee51ae3)


![image](https://github.com/user-attachments/assets/65b6c54b-0c7a-4ddd-b01b-03d526e8e5d2)
CPU
(1-(irate(node_cpu_seconds_total{instance="node-exporter:9100", mode="idle"}[1m])))* 100
CPULA
node_load1
node_load5
node_load15
Memory
node_memory_MemFree_bytes{instance="node-exporter:9100"}
Disk
node_filesystem_avail_bytes{instance="node-exporter:9100", device="/dev/mapper/centos-root"}
