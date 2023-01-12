# join-to-domain-windows
Ввод ПК в домен windows при помощи Ansible

## Инструкция по использованию

В inventory файл `ansible/hosts` указать имя ПК который вводится в домен.

    my-new-pc01

Для подключения к ПК с определенным именем пользотелем:

    my-new-pc01 ansible_user=root

## Запуск playbook
Для запуска необходимо передать extra-vars `target` с указанием ПК который вводится в домен.

    ansible]$ ansible-playbook playbooks/join-to-domain.yml --extra-vars "target=my-new-pc01"

если требуется пароль для sudo:

    ansible]$ ansible-playbook playbooks/join-to-domain.yml --extra-vars "target=my-new-pc01" --ask-become-pass

После запуска ввести запрошенные данные:

    Имя домена: (ваш домен)
    Имя компьютера: (имя компьютера под которым будет вход в домен)
    Имя администратора домена: (логин администратора домена)
    Пароль администратора домена: (пароль администратора домена)
