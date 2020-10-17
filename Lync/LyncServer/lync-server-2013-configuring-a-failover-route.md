---
title: 'Lync Server 2013: Настройка маршрута отработки отказа'
description: 'Lync Server 2013: Настройка маршрута отработки отказа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560495"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Настройка маршрута отработки отказа в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

В следующем примере показано, как администратор может определить маршрут отработки отказа на тот случай, если шлюз Dallas-GW1 отключается для проведения технического обслуживания или недоступен по иным причинам. В таблице ниже показаны изменения, которые нужно внести в конфигурацию.

### <a name="table-1-user-policy"></a>Таблица 1. Политика пользователя

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Политика пользователя</th>
<th>Использование телефонов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Политика звонков по умолчанию</p></td>
<td><p>Локальный</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Локальная политика в Редмонде</p></td>
<td><p>редмондлокал</p></td>
</tr>
<tr class="odd">
<td><p>Политика звонков в Далласе</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>Таблица 2. Маршруты

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Название маршрута</th>
<th>Шаблон номера</th>
<th>Использование телефонов</th>
<th>Магистрали</th>
<th>Шлюз</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Локальный маршрут в Редмонде</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d {7} ) $</p></td>
<td><p>Локальный</p>
<p>редмондлокал</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Red — GW1</p>
<p>Red — GW2</p></td>
</tr>
<tr class="even">
<td><p>Локальный маршрут в Далласе</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d {7} ) $</p></td>
<td><p>Локальный</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas — GW1</p></td>
</tr>
<tr class="odd">
<td><p>Универсальный маршрут</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Red — GW1</p>
<p>Red — GW2</p>
<p>Dallas — GW1</p></td>
</tr>
<tr class="even">
<td><p>Маршрут для пользователей в Далласе</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas — GW1</p></td>
</tr>
</tbody>
</table>


В таблице 1 использование телефона GlobalPSTNHopoff добавлено после использования телефона DallasUsers в политике звонков в Далласе. Это позволяет использовать для звонков, к которым применяется политика звонков в Далласе, маршруты, настроенные для использования телефонов GlobalPSTNHopoff, если маршрут, заданный для использования телефонов DallasUsers, недоступен.

</div>

<span> </span>

</div>

</div>

</div>

