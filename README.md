# Построение VLAN
![image](https://github.com/user-attachments/assets/083723b2-eb71-439b-b836-51c0a073704a)

## Эмулятор
* GNS3

## Оборудование
* Маршрутизатор Cisco 3745, [сконфигурированный как Etherswitch Router](https://docs.gns3.com/docs/using-gns3/beginners/switching-and-gns3/) (сочетает функции маршрутизатора и коммутатора)

## Добавление VLAN
Добавим две VLAN, чтобы логически разделить сеть на два изолированных сегмента. Это повысит безопасность и эффективность сети (например, широковещательный трафик будет ограничен своей VLAN).

![image](https://github.com/user-attachments/assets/da147f3c-e58b-45f3-be2e-b444b16f4be3)

Аналогично для ESW2

## Конфигурация портов на коммутаторах
На каждом коммутаторе сконфигурируем два порта доступа (access port) для cоздания линий доступа и два магистральных порта (trunk port) для создания транка. Линии доступа свяжут коммутаторы с конечными устройствами и будут передавать трафик только той VLAN, которой принадлежит конечное устройство. Транк свяжет магистральные порты двух коммутаторов и будет передавать [тегированный трафик](https://en.wikipedia.org/wiki/IEEE_802.1Q) обеих VLAN.

![image](https://github.com/user-attachments/assets/2adc9802-faa7-43ab-98ef-0515301571d6)

Аналогично для ESW2

## Агрегирование каналов
С помощью механизма _агрегирования каналов_ или _группирования портов_ (link aggregation, LAG, EtherChannel, NIC teaming) объединим два физических канала связи между коммутаторами в один логический.

![image](https://github.com/user-attachments/assets/81a7da44-1a16-45fc-ba39-1b7e43059ac0)
![image](https://github.com/user-attachments/assets/67963f72-03d3-4f55-a2bb-d2909d5aa2f3)
![image](https://github.com/user-attachments/assets/dffc611d-9ae5-4b88-a840-28f0cabbb65c)

Аналогично для ESW1
