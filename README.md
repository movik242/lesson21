# lesson21

**Домашнее задание**

Поднять три виртуалки </br>
Объединить их разными vlan</br>
поднять OSPF между машинами на базе Quagga;</br>
изобразить ассиметричный роутинг;</br>
сделать один из линков "дорогим", но что бы при этом роутинг был симметричным.</br>

До запуска ansible проверил пинг на соседние сервера через интерфейс eth3

![image](https://github.com/movik242/lesson21/assets/143793993/ec910def-71cd-4710-bd72-381a93cf93dd)

![image](https://github.com/movik242/lesson21/assets/143793993/54f9a2f4-3596-4ece-a92f-fa71029d7578)

![image](https://github.com/movik242/lesson21/assets/143793993/a012eb35-538c-4c76-aaae-f3c3b9131cb4)

запуск vagrantfile + playbook

После выполнения будет настроен асимметричный роутинг

![image](https://github.com/movik242/lesson21/assets/143793993/e95ab549-21b3-4497-90d8-894bafcca51e)

симметричный роутинг

Чтобы получить симметричный роутинг достаточно изменить значение в конфиге /etc/frr/frr.conf

Коментируем строку на router2

     !ip ospf cost 1000
     systemctl restart frr.service

![image](https://github.com/movik242/lesson21/assets/143793993/ef19e5f9-c03f-472c-8d4b-52e54e7e4bb8)

     
