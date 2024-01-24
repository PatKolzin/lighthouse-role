lighthouse-role
=========

Предназначена для конфигурирования операционных систем под управлением SystemD

Роль выполняет:

1. Установку nginx для использования в качестве веб-сервера
2. Клонирование git-репозитория Lighthouse с исходным кодом
3. Создание конфигурационного файла nginx для доступа к статическим ресурсам Lighthouse
4. Запуск nginx

Requirements
------------

1. CentOS
2. Предустановленная БД Clickhouse

Role Variables
--------------

`defaults/main.yml`:  
Параметры, определяющие домашнюю директорию Lighthouse и директория с конфигурационными файлами nginx: 

```
lighthouse_home_dir: "/usr/share/nginx/html/lighthouse"
nginx_config_dir: "/etc/nginx"
```

Dependencies
------------

Для установки Lighthouse требуется роль `ansible-clickhouse`: https://github.com/AlexeySetevoi/ansible-clickhouse  
(или аналогичная по функционалу роль).

Example Playbook
----------------

Пример добавления роли в playbook: 

```
- name: Install lighthouse
  hosts: lighthouse
  tags: lighthouse
  roles:
    - lighthouse-role
```

License
-------

BSD
