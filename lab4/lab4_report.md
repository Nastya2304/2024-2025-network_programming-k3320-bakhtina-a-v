# LAB 4

University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming)  
Year: 2024/2025  
Group: K3320  
Author: Bakhtina Anastasia Viacheslavovna  
Lab: Lab4  
Date of create: 22.05.2024  
Date of finished: 24.05.2024

## Цель

Изучить синтаксис языка программирования P4 и выполнить 2 задания обучающих задания от Open network foundation для ознакомления на практике с P4.

## Выполнение

### Задание 1

1. Был взят образ с сайта и через импорт конфигураций запущена машина в связи с тем, что путь через vagrant был без графического интерфейса.

![alt text](img/image.png)

2. Была запущена команда в первом задании.

```bash
make run
```

3. Была неуспешная попытка ping
   ![alt text](img/image-2.png)

4. Был изучен основной синтаксис p4. Основные моменты, которые потребуются, это:

- transition - перевод в другое состояние
- emit - возвращает в выходной пакет указанный header
  ![alt text](img/image1.png)
- select - аналог switch case, только для состояний

5. Дополним код парсера, а именно парсинг ipv4 хеадера или в противном случае переход с состояние accept, которое нужно для принятия следующих пакетов

![alt text](img/image2.png)

6. Дополним код ингресс для проверки и пересылки пакетов, изменяющий заголовки:

![alt text](img/image-x.png)

![alt text](img/image-1.png)

7. Дополним код депарсера, а именно создадим выходной пакет на основе входного

![alt text](img/image-y.png)

8. Запустим и получим успешные пинги

![alt text](img/image-3.png)

### Задание 2

1. Сразу приступим к коду.

2. Дополним код парсера: добавим состояние для туннеля и включим его в select.

![alt text](img/image-4.png)

3. Дополним код депарсера для туннеля, добавим в выходной заголовок:

![alt text](img/image-5.png)

4. Дополним код ingress: объявим новую таблицу mytunnel_exact и действие mytunnel_forward, записывающее порт.

![alt text](img/image-6.png)

5. Проверим корректность работы

![alt text](img/image-7.png)

![alt text](img/image-8.png)

## Схема работы

### Задание 1

![alt text](img/image-9.png)

### Задание 2

![alt text](img/image-10.png)
