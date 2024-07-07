# Site Monitor

Тестовое задание для асинхронного отслеживания доступности сайтов организаций из сформированного перечня.

## Установка

1. Клонируйте репозиторий:
    ```bash
    git clone https://github.com/yourusername/sitemonitor.git
    cd sitemonitor
    ```

2. Установите зависимости:
    ```bash
    pip install -r requirements.txt
    ```

## Использование

Для запуска мониторинга выполните:
```bash
python3.7 site_monitor.py
```

## Альтернативное использование

Вас интересует ноутбук `site_monitor.ipynb`

## Особенности использования
При запуске обратите внимание, что некоторые банки блокируют запросы не из России. Поэтому запускать файлы (в том числе ноутбук .ipynb) необходимо с локальной машины и \textbf{без} использования VPN.

## Реализованный функционал

Программа асинхронно проверяет доступность сайтов из перечня организаций (асинхронность необходима, чтобы избежать блокировки проверки, когда какой-то сайт долго не отвечает).

В случае отказа записывается лог: «Наименование организации – время отказа сайта – наименование ошибки». 
После восстановления работы ресурса записывается лог: «Наименование организации – время восстановление сайта». Лог сохраняется в файл `site_availability.log`. 

По завершении мониторинга или при его остановке генерируется отчет в файл `site_availability_report.txt`, содержащий информацию о времени работы и простоя каждого сайта.

Реализована принудительная остановка мониторинга по кнопке "Stop Monitoring".

В файлах `site_availability.log` и `site_availability_report.txt` сохранены примеры работы. Список сайтов находится в файле `site_monitor.py`.
