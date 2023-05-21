# Системы аутентификации и защиты от несанкционированного доступа

Лабораторная работа №1

## Цель

Вывести информацию о системе

## Исходные данные

1.  ОС Windows 10
2.  RStudio Desktop
3.  Интерпретатор языка R 4.3.0.

## План

1. Выполнить команду system2(“systeminfo”, stdout = TRUE)
2. Выполнить команду system(“wmic cpu get name”)
3. Выполнить команду system(“powershell.exe”, args = c(“Get-EventLog”, “-LogName”, “System”, “-Newest”, “30”), stdout = TRUE)

1\.  Выполнение команды system2("systeminfo", stdout = TRUE) для вывод информации о системе windows

```{r}
system2("systeminfo", stdout = TRUE)
```
```
Имя узла:                         DESKTOP-83KR26F
Название ОС:                      Майкрософт Windows 10 Pro
Версия ОС:                        10.0.19045 Н/Д построение 19045
Изготовитель ОС:                  Microsoft Corporation
Параметры ОС:                     Изолированная рабочая станция
Сборка ОС:                        Multiprocessor Free
Зарегистрированный владелец:      vivnniczkij@mail.ru
Зарегистрированная организация:   Н/Д
Код продукта:                     00330-80000-00000-AA187
Дата установки:                   24.05.2021, 23:51:04
Время загрузки системы:           21.05.2023, 21:57:04
Изготовитель системы:             System manufacturer
Модель системы:                   System Product Name
Тип системы:                      x64-based PC
Процессор(ы):                     Число процессоров - 1.
                                  [01]: Intel64 Family 6 Model 158 Stepping 12 GenuineIntel ~3696 МГц
Версия BIOS:                      American Megatrends Inc. 1502, 26.06.2019
Папка Windows:                    C:\WINDOWS
Системная папка:                  C:\WINDOWS\system32
Устройство загрузки:              \Device\HarddiskVolume2
Язык системы:                     ru;Русский
Язык ввода:                       ru;Русский
Часовой пояс:                     (UTC+03:00) Москва, Санкт-Петербург
Полный объем физической памяти:   16 302 МБ
Доступная физическая память:      8 155 МБ
Виртуальная память: Макс. размер: 23 470 МБ
Виртуальная память: Доступна:     11 927 МБ
Виртуальная память: Используется: 11 543 МБ
Расположение файла подкачки:      D:\pagefile.sys
Домен:                            WORKGROUP
Сервер входа в сеть:              \\DESKTOP-83KR26F
Исправление(я):                   Число установленных исправлений - 23.
                                  [01]: KB5022502
                                  [02]: KB4562830
                                  [03]: KB4577586
                                  [04]: KB4580325
                                  [05]: KB5003791
                                  [06]: KB5012170
                                  [07]: KB5015684
                                  [08]: KB5026361
                                  [09]: KB5006753
                                  [10]: KB5007273
                                  [11]: KB5011352
                                  [12]: KB5011651
                                  [13]: KB5014032
                                  [14]: KB5014035
                                  [15]: KB5014671
                                  [16]: KB5015895
                                  [17]: KB5016705
                                  [18]: KB5018506
                                  [19]: KB5020372
                                  [20]: KB5022924
                                  [21]: KB5023794
                                  [22]: KB5025315
                                  [23]: KB5005699
Сетевые адаптеры:                 Число сетевых адаптеров - 7.
                                  [01]: TAP-Windows Adapter V9
                                        Имя подключения: Подключение по локальной сети
                                        Состояние:       Носитель отключен
                                  [02]: Intel(R) Ethernet Connection (7) I219-V
                                        Имя подключения: Ethernet
                                        DHCP включен:    Да
                                        DHCP-сервер:     192.168.100.1
                                        IP-адрес
                                        [01]: 192.168.100.231
                                        [02]: fe80::2daf:f2aa:4a47:eb07
                                  [03]: TAP-ProtonVPN Windows Adapter V9
                                        Имя подключения: Подключение по локальной сети 2
                                        Состояние:       Носитель отключен
                                  [04]: Wintun Userspace Tunnel
                                        Имя подключения: ProtonVPN TUN
                                        Состояние:       Носитель отключен
                                  [05]: Famatech RadminVPN Ethernet Adapter
                                        Имя подключения: Radmin VPN
                                        DHCP включен:    Нет
                                        IP-адрес
                                        [01]: 26.110.4.28
                                        [02]: fe80::49f6:c579:88a8:dbfd
                                        [03]: fdfd::1a6e:41c
                                  [06]: VirtualBox Host-Only Ethernet Adapter
                                        Имя подключения: Ethernet 2
                                        DHCP включен:    Нет
                                        IP-адрес
                                        [01]: 192.168.56.1
                                        [02]: fe80::4216:45f0:e672:3363
                                  [07]: Hyper-V Virtual Ethernet Adapter
                                        Имя подключения: vEthernet (WSL)
                                        DHCP включен:    Нет
                                        IP-адрес
                                        [01]: 192.168.0.1
                                        [02]: fe80::8db1:cfe0:8f1d:f6f4
Требования Hyper-V:               Расширения режима мониторинга виртуальной машины: Да
                                  Виртуализация включена во встроенном ПО: Да
                                  Преобразование адресов второго уровня: Да
                                  Доступно предотвращение выполнения данных: Да
```    
2\. Выполнение команды system("wmic cpu get name") для информации о процессоре

```{r}
system2("cmd", args = c("/c", "wmic cpu get name"), stdout = TRUE)
```
```	
Name
Intel(R) Core(TM) i5-9600KF CPU @ 3.70GHz
```
3\. Выполнение команды system("powershell.exe", args = c("Get-EventLog", "-LogName", "System", "-Newest", "30"), stdout = TRUE) для получение информации о логах

```{r}
system2("powershell.exe", args = c("Get-EventLog", "-LogName", "System", "-Newest", "30"), stdout = TRUE)
```
```
    Index Time          EntryType   Source                 InstanceID Message
   ----- ----          ---------   ------                 ---------- -------
   62006 май 21 22:02  Information Microsoft-Windows...          102 Networking driver in Virtual Machine is loaded and the prot...
   62005 май 21 22:02  Information Microsoft-Windows...          102 Networking driver in Virtual Machine is loaded and the prot...
   62004 май 21 22:02  Information Microsoft-Windows...          232 NIC 7B0A9427-65C2-494B-893B-FA8B0851CA0F--F9AE3CB2-D5E6-4C6...
   62003 май 21 22:02  Information Microsoft-Windows...          233 The operation '7' succeeded on nic 7B0A9427-65C2-494B-893B-...
   62002 май 21 22:02  Information Microsoft-Windows...          264 Port BBA2B36B-FA93-4AB8-A537-C2C0AA1E0E93 (Friendly Name: F...
   62001 май 21 22:02  Information Microsoft-Windows...          233 The operation '8' succeeded on nic 0C6F6380-AD8A-4FF4-9406-...
   62000 май 21 22:02  Information Microsoft-Windows...          234 NIC 0C6F6380-AD8A-4FF4-9406-DDCEAAD355A2--8C7BD5F9-3978-43A...
   61999 май 21 22:00  Information Service Control M...   1073748864 Тип запуска службы "Фоновая интеллектуальная служба передач...
   61998 май 21 21:59  Information Microsoft-Windows...            5 Secure Trustlet NULL Id 0 and Pid 0 started with status 0.
   61997 май 21 21:59  Information Microsoft-Windows...          102 Networking driver in Virtual Machine is loaded and the prot...
   61996 май 21 21:59  Information Microsoft-Windows...          102 Networking driver in Virtual Machine is loaded and the prot...
   61995 май 21 21:59  Information Microsoft-Windows...          232 NIC 0C6F6380-AD8A-4FF4-9406-DDCEAAD355A2--8C7BD5F9-3978-43A...
   61994 май 21 21:59  Information Microsoft-Windows...          233 The operation '7' succeeded on nic 0C6F6380-AD8A-4FF4-9406-...
   61993 май 21 21:59  Information Microsoft-Windows...          264 Port F6B44DF7-AE5A-4017-A2C7-47EF72557D09 (Friendly Name: 8...
   61992 май 21 21:59  Information Microsoft-Windows...          232 NIC E14FAE3F-F3FC-4433-8EB2-877088116011 (Friendly Name: WS...
   61991 май 21 21:59  Information Microsoft-Windows...            7 Miniport NIC E14FAE3F-F3FC-4433-8EB2-877088116011 (Friendly...
   61990 май 21 21:59  Information Microsoft-Windows...          233 The operation '7' succeeded on nic E14FAE3F-F3FC-4433-8EB2-...
   61989 май 21 21:59  Information Microsoft-Windows...          264 Port D594E8BD-48A5-43A1-9F48-36AF68CFC09A (Friendly Name: C...
   61988 май 21 21:59  Information Microsoft-Windows...            9 Switch 3514085C-5CB9-42D7-98D6-9132C6EFF6F8 (Friendly Name:...
   61987 май 21 21:59  Information Microsoft-Windows...          232 NIC 3514085C-5CB9-42D7-98D6-9132C6EFF6F8 (Friendly Name: WS...
   61986 май 21 21:59  Information Microsoft-Windows...          233 The operation '7' succeeded on nic 3514085C-5CB9-42D7-98D6-...
   61985 май 21 21:58  Warning     DCOM                        10016 Не найдено описание для события с кодом '10016' в источнике...
   61984 май 21 21:57  Information Service Control M...   1073748864 Тип запуска службы "Фоновая интеллектуальная служба передач...
   61983 май 21 21:57  Warning     DCOM                        10016 Не найдено описание для события с кодом '10016' в источнике...
   61982 май 21 21:57  Information Service Control M...   3221232498 Следующие драйверы загрузки или запуска системы не загружен...
   61981 май 21 21:57  Warning     DCOM                        10016 Не найдено описание для события с кодом '10016' в источнике...
   61980 май 21 21:57  Information Microsoft-Windows...          233 The operation '8' succeeded on nic 5EC32C01-E840-4998-9790-...
   61979 май 21 21:57  Warning     DCOM                        10016 Не найдено описание для события с кодом '10016' в источнике...
   61978 май 21 21:57  Information Microsoft-Windows...           62 Переключение A7ED344C-F6C6-4E9B-B642-FB01AB28424D (понятное...
   61977 май 21 21:57  Information Microsoft-Windows...          233 The operation '8' succeeded on nic A7ED344C-F6C6-4E9B-B642-...
```  
## Оценка результата

В результате лабораторной работы была получена информация о процессоре, об операционной системе и о последних логах

## Вывод

В результате выполнения работы были получены навыки работы с командами Windows через среду разработки RStudio
