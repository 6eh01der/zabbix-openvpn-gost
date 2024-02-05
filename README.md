# zabbix-openvpn-gost

Fork of https://github.com/Grifagor/zabbix-openvpn adopted for OpenVPN-GOST (https://www.cryptocom.ru/products/openvpn.html)

Script for OpenVPN-GOST users monitoring.
It shows an OpenVPN-GOST user’s status, and its uplink and downlink traffic.
The “items” by the files certificates names are made using LLD.
Additionally this template contains OpenVPN-GOST systemd unit status monitoring.

Setup:

1) Enable OpeVPN-GOST server status log by adding "status openvpn-gost-status.log" string to server config, for Ubuntu "/etc/openvpn-gost/openvpn-gost.conf", or change status log file name and path in "/etc/zabbix/zabbix_agent2.d/openvpn-gost.conf";

2) Copy the file discover_vpn.sh to any directory on the server were OpenVPN-GOST is (for example /etc/zabbix/zabbix_agent2.d/scripts/discover_vpn.sh ), in this file specify the path to directory where OpenVPN-GOST users configs are (line №3), change owner to zabbix and make it executable;

3) Copy "openvpn-gost.conf" file from this repo into zabbix_agent2.d directory (for example /etc/zabbix/zabbix_agent2.d/openvpn-gost.conf), probably, will be necessary to change the path to  discover_vpn.sh;

4) Import openvpn-gost.yaml to zabbix template.

# zabbix-openvpn-gost 

Форк https://github.com/Grifagor/zabbix-openvpn адаптированный для OpenVPN-GOST (https://www.cryptocom.ru/products/openvpn.html)

Скрипт мониторинга пользователей OpenVPN-ГОСТ.
Проверяется статус каждого пользователя OpenVPN-ГОСТ, и его входящий\исходящий трафик.
С помощью LLD создаются "элементы данных" по имени файлов сертификатов.
Дополнительно этот шаблон включает мониторинг состония systemd юнита OpenVPN-ГОСТ.

Установка:

1) Включите OpeVPN-ГОСТ логирование статуса клиентов добавив строку "status openvpn-gost-status.log" в конфигурационный файл сервера, в случае Ubuntu "/etc/openvpn-gost/openvpn-gost.conf", или изменив имя статусного лог файла и путь к нему в "/etc/zabbix/zabbix_agent2.d/openvpn-gost.conf";

2) Скопировать файл discover_vpn.sh в любую директорию, на сервере с OpenVPN-ГОСТ (например, /etc/zabbix/zabbix_agent2.d/scripts/discover_vpn.sh), указать в нём путь до папки с клиентскими конфигурациями OpenVPN-ГОСТ (строка №3), сделать владельцем пользователя zabbix и дать права на выполнение;
	
3) Скопировать файл "openvpn-gost.conf" этого репозитория в zabbix_agent2.d (например /etc/zabbix/zabbix_agent2.d/openvpn-gost.conf), возможно потребуется изменить путь до discover_vpn.sh;
	
4) Импортировать в zabbix шаблон openvpn-gost.yaml
