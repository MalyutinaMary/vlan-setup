# Компьютерные сети

## Настройка NTP

>`sh clock`
>
>`clock set HH:MM:SS MONTH DAY YEAR`
>
>`sh ntp status`
>
>`sh ntp associations`
>
>(config) `ntp server <ip-address>`
>
>(config) `ntp master`
>
>(config) `ntp source <ip-address>`

## Настройка DNS

>Необходимо добавить loopback-интерфейс для корректного разрешения добавленного DNS-имени в IP. Не использовать диапазон адресов 127.0.0.0/8, чтобы loopback-интерфейс был доступен внешним устройствам.
>
>(config) `int Loopback0`
>
>(config-if) `ip add <ip-address>`
>  
>Настройка DNS-сервера:
>
>(config) `ip dns server`
>
>(config) `ip host <host-name> <ip-address>`
>  
>Настройка DNS-клиента:
>
>(config) `ip name-server <ip-address>`
>
>(config) `ip domain lookup`

## Настройка DNS
>(config) `ip dhcp excluded-address <low-address> <high-address>`
>
>(config) `ip dhcp pool <POOL_NAME>`
>
>(dhcp-config) `network <subnet> <subnet-mask>`
>
>(dhcp-config) `dns-server <ip-address>`
>
>(dhcp-config) `default-router <ip-address>`
>
>(dhcp-config) `lease 0 5 30`

## Настройка SSH

Установка пароля:
>(config) `aaa new-model`
>
>(config) `username admin`
>
>(config) `username admin secret <admin-password>`
>
>(config) `enable secret <privileged-password>`
>
>Настройка соединения по SHH:
>
>(config) `hostname <new-hostname>`
>
>(config) `ip domain-name <new-domain-name>`
>
>(config) `crypto key generate rsa`
>
>(config) `line vty 0 4`
>
>(config-line) `transport input ssh`
>
>Настройка версии SSH:
>
>`sh ip ssh`
>
>(config) `ip ssh version 2`
>
>Подключение к удаленному устройству по SSH:
>
>`ssh -l <username> <ip-address>`

## Построение VLAN

![image](https://github.com/user-attachments/assets/083723b2-eb71-439b-b836-51c0a073704a)


### Добавление VLAN
![image](https://github.com/user-attachments/assets/da147f3c-e58b-45f3-be2e-b444b16f4be3)
### Конфигурация портов на коммутаторе
![image](https://github.com/user-attachments/assets/2adc9802-faa7-43ab-98ef-0515301571d6)
### Проверка соединения
![image](https://github.com/user-attachments/assets/a66e9f3e-0300-4acf-84b2-befba4eb5470)
![image](https://github.com/user-attachments/assets/c4f5a86e-1574-45bd-99da-c9c0de62db12)
### Агрегирование каналов
![image](https://github.com/user-attachments/assets/81a7da44-1a16-45fc-ba39-1b7e43059ac0)
![image](https://github.com/user-attachments/assets/67963f72-03d3-4f55-a2bb-d2909d5aa2f3)
![image](https://github.com/user-attachments/assets/dffc611d-9ae5-4b88-a840-28f0cabbb65c)
