---
title: 'Lync Server 2013: настройка таблицы орбит парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417fb90feb9f12f8c2776518fa8fefffae7ff003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Настройка таблицы орбит парковки вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-10_

Метод парковки использует орбиты для вызовов парковки. Прежде чем пользователи смогут приступить к приостановке и получению звонков, необходимо настроить таблицу "Орбита". Вы должны указать диапазоны добавочных номеров (орбиты), которые ваша организация резервирует для звонков на стоянку, и определить маршрут для этих диапазонов, указав, какой пул приостановки вызова обрабатывает каждый из диапазонов. When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services. Вы можете создать несколько диапазонов орбиты на приостановку для каждого пула серверов Lync Server, в котором развернуто приложение для приостановки звонков. Для каждого диапазона орбиты на линии с приостановкой на начало работы должны быть заданы глобально уникальное имя и уникальный набор расширений.

<div>


> [!IMPORTANT]  
> Обычно диапазон орбит содержит 100 или менее орбит. Каждый из диапазонов может быть значительно больше, максимальные значения составляют не более 10000 орбит на диапазон и менее 50000 орбит на пул. Если диапазон слишком мал, орбиты используются повторно с большей частотой.



</div>

Для своих диапазонов орбит используйте блоки виртуальных добавочных номеров (которым не назначен телефон или пользователь).

<div>


> [!NOTE]  
> Не поддерживается назначение прямых и непосредственных номеров для нумерации на орбите в таблице "набрать на орбиту".



</div>

<div>

## <a name="in-this-section"></a>Содержание

[Создание или изменение диапазона орбиты на расстоянии вверх на сервере Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

