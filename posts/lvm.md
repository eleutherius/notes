﻿#####Linux Volume Manager (LVM)

**Linux Volume Manager (LVM)** - это мощная система управления томами с данными для Linux. Она позволяет создавать поверх физических разделов (или даже неразбитых винчестеров) логические тома, которые в самой системе будут видны как обычные блочные устройства с данными (т.е. как обычные разделы). Основные преимущества LVM в том, что во-первых одну группу логических томов можно создавать поверх любого количества физических разделов, а во-вторых размер логических томов можно легко менять прямо во время работы. Кроме того, LVM поддерживает механизм снапшотов, копирование разделов «на лету»



#### Терминология

Поскольку система управления логическими томами использует собственную модель представления дискового пространства, нам необходимо определиться с терминами и взаимосвязями понятий. Рассмотрим схему, основанную на диаграмме Эрика Бегфорса (Erik Bеgfors), приведенную им в списке рассылки linux-lvm. Она демонстрирует взаимосвязь понятий системы LVM:







#### Обозначения и понятия:



------------



**PV**, Physical volume, физический том. Обычно это раздел на диске или весь диск. В том числе, устройства программного и аппаратного RAID (которые уже могут включать в себя несколько физических дисков). Физические тома входят в состав группы томов.



------------



**VG**, Volume group, группа томов. Это самый верхний уровень абстрактной модели, используемой системой LVM. С одной стороны группа томов состоит из физических томов, с другой -- из логических и представляет собой единую административную единицу.



------------





**LV**, Logical volume, логический том. Раздел группы томов, эквивалентен разделу диска в не-LVM системе. Представляет собой блочное устройство и, как следствие, может содержать файловую систему.



------------





**PE**, Physical extent, физический экстент. Каждый физический том делится на порции данных, называющиеся физическими экстентами. Их размеры те же, что и у логических экстентов.



------------





**LE**, Logical extent, логический экстент. Каждый логический том делится на порции данных, называющиеся логическими экстентами. Размер логических экстентов не меняется в пределах группы томов.



------------


