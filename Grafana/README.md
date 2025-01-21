# Домашнее задание к занятию 14 «Средство визуализации Grafana»

### Задание 1

1. Используя директорию [help](./help) внутри этого домашнего задания, запустите связку prometheus-grafana.
1. Зайдите в веб-интерфейс grafana, используя авторизационные данные, указанные в манифесте docker-compose.
1. Подключите поднятый вами prometheus, как источник данных.
1. Решение домашнего задания — скриншот веб-интерфейса grafana со списком подключенных Datasource.

--------

### Ответ
![image](https://github.com/user-attachments/assets/d6db79e9-5370-4305-b60d-06bdf9520edb)
![image](https://github.com/user-attachments/assets/ef33daf8-3327-4afe-a9c4-7350df1a2500)
![image](https://github.com/user-attachments/assets/0faf0717-5511-4ec6-951b-c128275c1c42)


Вводим идентификатор дашборда. Для Node Exporter это 1860:
![image](https://github.com/user-attachments/assets/fcd6b126-a2a0-4414-8d01-add0116a81bb)

## Задание 2

Изучите самостоятельно ресурсы:

1. [PromQL tutorial for beginners and humans](https://valyala.medium.com/promql-tutorial-for-beginners-9ab455142085).
1. [Understanding Machine CPU usage](https://www.robustperception.io/understanding-machine-cpu-usage).
1. [Introduction to PromQL, the Prometheus query language](https://grafana.com/blog/2020/02/04/introduction-to-promql-the-prometheus-query-language/).

Создайте Dashboard и в ней создайте Panels:

- утилизация CPU для nodeexporter (в процентах, 100-idle);
- CPULA 1/5/15;
- количество свободной оперативной памяти;
- количество места на файловой системе.

Для решения этого задания приведите promql-запросы для выдачи этих метрик, а также скриншот получившейся Dashboard.

--------

### Ответ
![image](https://github.com/user-attachments/assets/65b6c54b-0c7a-4ddd-b01b-03d526e8e5d2)
CPU

- (1-(irate(node_cpu_seconds_total{instance="node-exporter:9100", mode="idle"}[1m])))* 100

CPULA
- node_load1
- node_load5
- node_load15
- 
Memory
- node_memory_MemFree_bytes{instance="node-exporter:9100"}

Disk
- node_filesystem_avail_bytes{instance="node-exporter:9100", device="/dev/mapper/centos-root"}

## Задание 3

1. Создайте для каждой Dashboard подходящее правило alert — можно обратиться к первой лекции в блоке «Мониторинг».
1. В качестве решения задания приведите скриншот вашей итоговой Dashboard.

--------

### Ответ
Alert в Prometheus
![image](https://github.com/user-attachments/assets/a7403e4e-4796-4a50-86d9-fb500f4070aa)
![image](https://github.com/user-attachments/assets/0ecb3917-24af-4e5a-92b9-07283ee51ae3)

Alert Grafana
![image](https://github.com/user-attachments/assets/aed4d1db-3b8b-43dc-8af0-28e33b0d4ff1)

## Задание 4

1. Сохраните ваш Dashboard.Для этого перейдите в настройки Dashboard, выберите в боковом меню «JSON MODEL». Далее скопируйте отображаемое json-содержимое в отдельный файл и сохраните его.
1. В качестве решения задания приведите листинг этого файла.

[Dashboard](Grafana/Dashboard.json)

---
