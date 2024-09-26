# Prometheus
### Установка Prometheus сервера с помощью скрипта
Запуск скрипта:
```
sudo ./install_prometheus_server.sh
```
Проверка сервиса:
```
sudo systemctl status prometheus
```
##### Веб интерфейс доступен на порту 9090

Добавление серверов к мониторингу:
```
sudo nano /etc/prometheus/prometheus.yml
```
Создаем категорию для серверов и добавляем ip адреса серверов и порт который слушает node exporter (agent)
```
  - job_name      : "ubuntu-servers"
    static_configs:
      - targets:
          - 10.0.0.1:9100
          - 10:0.0.2:9100
```
Перезапуск сервиса для обновления списка:
```
sudo systemctl restart prometheus
```


### Мониторинг Linux сервера
Устанавливаем node exporter (agent) который будет собирать метрики о операционной системе
Запуск скрипта:
```
sudo ./install_node_exporter.sh
```
Метрики будут доступны на порту 9100
