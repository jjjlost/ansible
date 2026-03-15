Файл со списком хостов
host.ini
Запускаем роль командой ansible-playbook -i host.ini zabbix_server.yml
Структура роли
roles/
└── zabbix_install
    ├── defaults
    │   └── main.yml  Здесь указываем переменные
    ├── handlers
    │   └── main.yml   перезапускает стек Zabbix при изменении
    ├── tasks
    │   ├── apt.yml    Обновляем репозитарии и систему
    │   ├── docker.yml Ставим докер
    │   ├── main.yml   Прописываем состав роли
    │   └── zabbix_container.yml Устанавливаем zabbix в роль
    └── templates
        ├── docker-compose.zabbix.yml.j2  шаблон для Docker
        └── nginx.conf.j2                 шаблон для веб сервера

Сертификат для https самоподписанный, для тестирования на локальных хостах, в проде изменить на то что нужно.
