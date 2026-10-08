# Network

Раздел посвящён сетевым технологиям: конфигурация оборудования, протоколы, диагностика.

## Подразделы

- [Huawei](Huawei/index.md) — базовая настройка и команды VRP

## Базовые команды Huawei VRP

### Просмотр информации

| Команда | Описание |
|---|---|
| `display version` | Версия ПО и информация об устройстве |
| `display device` | Состояние плат и модулей |
| `display interface brief` | Краткая сводка по интерфейсам |
| `display ip interface brief` | IP-адреса интерфейсов |
| `display current-configuration` | Текущая конфигурация |
| `display saved-configuration` | Сохранённая конфигурация |

### Навигация и режимы

```
system-view                     # Переход в системный вид
sysname SW-01                   # Задать имя устройства
quit                            # Выход на уровень выше
return                          # Выход в привилегированный режим
save                            # Сохранить конфигурацию
```

### Диагностика

```
ping 10.0.0.1                   # Проверка доступности
display interface GigabitEthernet0/0/1   # Подробно об интерфейсе
display mac-address             # Таблица MAC-адресов
display arp                     # Таблица ARP
```
