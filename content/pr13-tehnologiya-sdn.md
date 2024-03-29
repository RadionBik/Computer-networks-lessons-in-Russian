pr13-tehnologiya-sdn

# Практическая работа 13. Технология SDN

Цель: понять принципы технологии SDN и освоить базовые навыки работы в Mininet.

Практически каждое _управляемое_ сетевое устройство функционально может быть разделено на следующие уровни:

* data plane \([forwarding plane](https://en.wikipedia.org/wiki/Forwarding_plane)\) -- уровень передачи данных, для которого характерна скоростная коммутация \(или маршрутизация\) пакетов без необходимости "консультации" с CPU устройства, основываясь на информации из Forwarding Information Base \([FIB](https://en.wikipedia.org/wiki/Forwarding_information_base), обобщение понятия MAC-таблицы\).  
* control plane -- уровень управления устройства, где происходит ресурсоемкая задача обработки пакетов, управляющих системой. Примерами подобных сообщений являются BPDU, LSA, SSH и т.д. 

SDN \(software-defined networks\) -- технология, для которой характерно выделение control plane из сетевых узлов и с последующим его выносом на централизованный котроллер сети. Подобная централизация сетевого интеллекта позволяет сетевым администраторам программно контролировать, менять и управлять сетью через открытые интерфейсы, представляющие новый уровень абстракции для функционала низкого уровня. Технология создана для устранения недостатков статической архитектуры сетей, которая плохо справляется с проблемами динамичных масштабируемых сред, таких как сети датацентров. SDN изначально ассоциировали только с протоколом [OpenFlow](https://en.wikipedia.org/wiki/OpenFlow), который появился в 2011 г., однако с тех пор, ряд компаний \(Cisco, Nicira\) представили свои реализации протоколов для SDN.

OpenFlow -- коммуникационный протокол, позволяющий получить доступ контроллеру к data-plane сетевого устройства. С его помощью, контроллер может задавать более гибкие политики управления трафиком, чем те, которые обеспечиваются ACLs и протоколами маршрутизации в традиционных сетях.  Более того, посредством единого открытого протокола OpenFlow, возможно управлять коммутаторами даже различных производителей. Протокол использует TCP на транспортном уровне, также обеспечена поддержка [Transport Layer Security](https://en.wikipedia.org/wiki/Transport_Layer_Security) \(TLS\). Коммутаторы подключаются к контроллеру через TCP порт 6653.

В этой работе, для эмуляции работы сети используется среда Mininet, которая позволяет создавать прототипы SDN-сетей на своем ПК. В качестве коммутаторов используется программные коммутаторы [Open vSwitch](https://en.wikipedia.org/wiki/Open_vSwitch), а контоллер по умолчанию -- [POX](http://www.noxrepo.org/).

Для начала работы, скачайте образ с Mininet для VirtualBox:

```
https://github.com/mininet/mininet/wiki/Mininet-VM-Images
```

Проследуйте за процессом установки образа:

```
http://mininet.org/vm-setup-notes/
```

Официальная инструкция для начала работы в среде:

```
http://mininet.org/walkthrough/
```

В случае неясностей, просмотрите видео на YouTube:

```
https://www.youtube.com/watch?v=jmlgXaocwiE
```

> Для подключения к консоли виртуальной машины можно использовать _Putty_.

**Задание**

1. Запустите в Mininet топологию с 4 коммутаторами и 4-я подключенными к ним хостами.

2. Проверьте топологию, выполнив соответствующую команду.

3. Выполните команду ping между любыми двумя хостами. Что интересного можете выделить, анализируя вывод команды?

4. Запустите _Wireshark_ или _tcpdump_ на Loopback0 интерфейсе, повторив все предыдущие шаги. Отфильтруйте OpenFlow протокол и проанализируйте содержимое пакетов. Какие типы пакетов встречаются в вашей сети?  Какие поля содержатся у пакетов типа _of\_flow\_add?_

5. Сделайте выводы.

