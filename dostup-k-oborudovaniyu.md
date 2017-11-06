# Доступ к оборудованию кафедры РТС

## Доступ к серверу \(502б\) по RDP:

| Address | 10.85.4.40 |
| :--- | :--- |
| Domain | stud |
| Login | rts\_userX \(X от 1 до 10\) |
| Password | 87654321 |

## Доступ к Packet Tracer 7.x:

| Поле | Значение |
| :--- | :--- |
| Login | rtskai |
| Password | RTSiret5knrtu |

## Доступ к EVE-NG:

EVE-NG– платформа виртуализации образов IOL, vIOS, IOS-XRv, dynamips, qemu и т.д.

Для полного перечня доступных функций посетите сайт:  [http://eve-ng.net](http://eve-ng.net/)

Для удобства подключения к консолям устройств и сниффинга трафика в Wireshark, можно установить пакет интеграции для Windows:

[http://eve-ng.net/index.php/downloads/windows-client-side-pack](http://eve-ng.net/index.php/downloads/windows-client-side-pack)

Доступ из кафедральной сети реализован посредством Port Forwarding:

| Подключение | Внутри 501 | Из кафедры РТС |
| :--- | :--- | :--- |
| HTTP | 192.168.101.150:80 | 10.85.4.14:8080 |
| SSH | 192.168.101.150:22 | 10.85.4.14:2222 |
| EVE-NG nodes | 192.168.101.150:32700-32800 | 10.85.4.14:32700-32800 |

| Поле \(при подключении по HTTP\) | Значение |
| :--- | :--- |
| Login | student |
| Password | kai |



