University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming)

Year: 2025

Group: K3323

Author: Vlasov Aleksandr Alekseevich

Lab: Lab1

Date of create: 28.03.2025

Date of finished:

### Настройка сервера

Создаем прерываемую виртуалку в Яндекс облаке, скачиваем клиент Amnezia, указываем запрашиваемые данные

![](image.png)

Протокол -- TCP

![](image-1.png)


После создания пользователя экспортируем конфиг .ovpn

Убираем из конца блок:

```
redirect-gateway def1 ipv6 bypass-dhcp
ifconfig-ipv6 fd15:53b6:dead::2/64  fd15:53b6:dead::1
block-ipv6
```

И из начала:

```
dhcp-option DNS 1.1.1.1
dhcp-option DNS 1.0.0.1
```

Создаем локально виртуалку в VirtualBox

![](image-2.png)

Заходим на выданный адрес в Winbox

В файлах загружаем конфиг

![](image-3.png)

Идем в PPP и импортируем

![](image-4.png)

После включаем интерфейс

![](image-5.png)

Чтобы проверить можно зайти на сервер посмотреть его ip в локальной сети

![](image-6.png)

И пингануть с микротика

![](image-7.png)
