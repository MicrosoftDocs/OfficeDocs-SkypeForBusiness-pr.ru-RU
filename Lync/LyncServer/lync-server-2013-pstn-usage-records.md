---
title: 'Lync Server 2013: записи об использовании PSTN'
description: 'Lync Server 2013: записи об использовании PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565585"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a>Записи использования PSTN в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-23_

Планирование режимов работы с ТСОП в основном состоит из составления списка всех разрешений звонков, действующих в организации, начиная с генерального директора и заканчивая временными работниками, консультантами и работниками по контракту. Этот процесс позволяет перепроверять существующие разрешения звонков и вносить в них изменения. Вы можете создавать режимы работы с ТСОП только для тех разрешений звонков, которые будут применяться к предполагаемым пользователям корпоративной голосовой связи. Однако более рационально создавать режимы работы с ТСОП для всех разрешений звонков независимо от того, будут ли некоторые из них в настоящее время применяться к группе пользователей, включаемых для корпоративной голосовой связи. При изменении разрешений звонков или добавлении новых пользователей с разными разрешениями звонков требуемые режимы работы с ТСОП уже будут созданы.

В следующей таблице приведены типичные режимы работы с ТСОП.

### <a name="pstn-usage-records"></a>Режимы работы с ТСОП

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
<td><p>Локальный</p></td>
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
<td><p>Дели</p></td>
<td><p>Штатные сотрудники, расположенные в г. Дели</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Штатные сотрудники, расположенные в г. Редмонд</p></td>
</tr>
<tr class="even">
<td><p>Назвать ее redmondtemps</p></td>
<td><p>Временные сотрудники, расположенные в г. Редмонд</p></td>
</tr>
<tr class="odd">
<td><p>Цюрихе</p></td>
<td><p>Штатные сотрудники, расположенные в г. Цюрих</p></td>
</tr>
</tbody>
</table>


Сами по себе режимы работы с ТСОП не выполняют никаких действий. Чтобы режимы работы с ТСОП начали работать, необходимо связь их со следующими данными:

  - Политики голосовых служб, назначенные пользователям.

  - Маршруты, назначенные номерам телефонов.

Дополнительные сведения о политиках голосовой связи и маршрутах приведены в статье [политики голосовой связи в Lync server 2013](lync-server-2013-voice-policies.md) и [маршруты голосовых вызовов в Lync Server 2013](lync-server-2013-voice-routes.md). Сведения о том, как создавать и настраивать [маршруты голосовой связи, приведены в статье Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

