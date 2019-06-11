---
title: 'Lync Server 2013: записи использования ТСОП'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Записи использования ТСОП в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-23_

Планирование записей использования PSTN включает в себя список всех разрешений на звонки, которые в настоящее время используются в вашей организации, от Генерального директора до временных сотрудников, консультантов и сотрудников по договору. Кроме того, этот процесс позволяет повторно проверить существующие разрешения на вызов и исправить их. Вы можете создавать записи об использовании PSTN только для тех разрешений на звонки, которые применяются к предполагаемым пользователям голосовой связи, но это решение может создавать записи использования PSTN для всех разрешений на звонки, независимо от того, могут ли в данный момент отсутствовать некоторые из них. применить к группе пользователей, которые должны быть включены в рамках корпоративной голосовой связи. Если добавлены разрешения на вызов изменение или добавление новых пользователей с разными разрешениями на вызов, вы будете уже созданы нужные записи использования PSTN.

В следующей таблице приведены типичные режимы работы с ТСОП.

### <a name="pstn-usage-records"></a>Записи использования ТСОП

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Атрибут номера</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>Местные звонки</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>Междугородние звонки</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>Международные звонки</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Штатные сотрудники, расположенные в г. Дели</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Штатные сотрудники, расположенные в г. Редмонд</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Временные сотрудники, расположенные в г. Редмонд</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>Штатные сотрудники, расположенные в г. Цюрих</p></td>
</tr>
</tbody>
</table>


Сами по себе режимы работы с ТСОП не выполняют никаких действий. Чтобы режимы работы с ТСОП начали работать, необходимо связь их со следующими данными:

  - Политики голосовых служб, назначенные пользователям.

  - Маршруты, назначенные номерам телефонов.

Дополнительные сведения о политиках голосовой связи и маршрутах можно найти в разделе [политики голосовой связи в Lync server 2013](lync-server-2013-voice-policies.md) и [Голосовые маршруты в Lync Server 2013](lync-server-2013-voice-routes.md). Подробнее о том, как создать и настроить их, можно найти [в разделе Настройка голосовых маршрутов для исходящих звонков в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

