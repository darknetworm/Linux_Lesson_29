# Linux_Lesson_29
## Traffic filtering

### Описание репозитория

Лабораторный стенд для тестирования сетевой инфраструктуры с пробросом портов веб сервера, использованием шлюза по умолчанию для доступа к сети интернет и использованием port knocking для доступа к шлюзу, настраиваемые с использованием Vagrant и Ansible. Все файлы и структуру директорий temрlates и roles необходимо скопировать в общую директорию.

**Vagrantfile** - создает виртуальные машины: сервер (centralserver), шлюз для выхода в интернет (inetrouter), шлюз доступа к веб-серверу с пробросом портов (inetrouter2) и центральный маршрутизатор (centralrouter). Настройка функциональности хостов производится с помощью Ansible.
