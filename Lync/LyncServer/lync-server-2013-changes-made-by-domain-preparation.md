---
title: 'Lync Server 2013: изменения, внесенные при подготовке домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Изменения, внесенные при подготовке домена в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2010-10-18_

В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в корневом домене. Все записи ACE наследуются, если не указано иное.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>Записи ACE, добавленные в корневой домен

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>Рткуниверсал — Усерреадонли — группа</th>
<th>Рткуниверсал — Серверреадонли — группа</th>
<th>Рткуниверсал — Усерадминс</th>
<th>Ртчсуниверсал — службы</th>
<th>Прошедшие проверку — пользователи</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Чтение контейнера (не наследуется)</p></td>
<td><p><strong>Да</strong></p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение User PropertySet Personal-Information</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение User PropertySet General-Information</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение User PropertySet Public-Information</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
</tr>
<tr class="odd">
<td><p>Чтение User PropertySet RTCPropertySet</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Запись User Property Proxy-Addresses</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Запись User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Запись User PropertySet RTCPropertySet</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение PropertySet DS-Replication-Get-Changes всех объектов Active Directory</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
</tr>
</tbody>
</table>


В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в трех встроенных контейнерах: «Пользователи», «Компьютеры», «Контроллеры доменов». Все записи ACE наследуются, если не указано иное.

### <a name="aces-added-to-built-in-containers"></a>Записи ACE, добавленные во встроенные контейнеры

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>Рткуниверсал — Усерреадонли — группа</th>
<th>Рткуниверсал — Серверреадонли — группа</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Чтение контейнера (не наследуется)</p></td>
<td><p><strong>Да</strong></p></td>
<td><p><strong>Да</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

