## OTUS Administrator Linux. Professional ДЗ №11: Ansible

**Задание**
Подготовить стенд на Vagrant как минимум с одним сервером. На этом сервере используя Ansible необходимо развернуть nginx со следующими условиями:

1. Необходимо использовать модуль yum/apt;
2. Конфигурационные файлы должны быть взяты из шаблона jinja2 с перемененными;
3. После установки nginx должен быть в режиме enabled в systemd;
4. Должен быть использован notify для старта nginx после установки;
5. Сайт должен слушать на нестандартном порту - 8080, для этого использовать переменные в Ansible.

**_Решение_**

Стенд состоит из 1 ВМ, разворот осуществляется при помощи Vagrant ([vagrantfile](./Vagrantfile)), дальнейшая настройка - при помощи Ansible ([playbook](./playbook.yml)).
Конфигурационный файл nginx берётся из [шаблона](./nginx.conf.j2), текст index.html - также из [шаблона](./index.html.j2).

Для тестирования - с ВМ пробрасывается порт 8080 на порт хоста 8081.

Скриншот браузера:
![screenshot](./hello.png)
