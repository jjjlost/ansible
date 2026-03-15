Файл со списком хостов

host.ini

Запускаем роль командой ansible-playbook -i host.ini zabbix_server.yml

Структура роли

Структура роли

```
roles/
└── zabbix_install
    ├── defaults
    │   └── main.yml
    │       переменные роли
    │
    ├── handlers
    │   └── main.yml
    │       перезапускает стек Zabbix
    │
    ├── tasks
    │   ├── apt.yml
    │   │       обновление системы
    │   │
    │   ├── docker.yml
    │   │       установка Docker
    │   │
    │   ├── main.yml
    │   │       основной файл роли
    │   │
    │   └── zabbix_container.yml
    │           запуск контейнеров Zabbix
    │
    └── templates
        ├── docker-compose.zabbix.yml.j2
        └── nginx.conf.j2
```

Сертификат для https самоподписанный, для тестирования на локальных хостах, в проде изменить на то что нужно.


