---
title: 'Lync Server 2013: сводка по DNS — единственный директор'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1eaaebf1fb695bc1ee6ea1b86f980a666cf0a70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515536"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a>Сводка по DNS — единственный директор в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

В следующей таблице представлена сводная информация о записях DNS, необходимых для поддержки одного директора. Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана. Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора. От сервера переднего плана директор не размещает учетные записи пользователей или не размещает службы Mobility Service.

### <a name="dns-records-required-for-the-director"></a>Записи DNS, необходимые для директора

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение/тип/порт</th>
<th>Полное доменное имя/Запись DNS</th>
<th>IP-адрес/Полное доменное имя</th>
<th>Сопоставляется с/комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Директор</p></td>
<td><p>Запись узла директора, используемая для репликации и сервера на сервер</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Директор</p></td>
<td><p>Входящий протокол SIP из внутреннего пограничного интерфейса пограничного сервера</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Директор</p></td>
<td><p>Опубликованные веб-службы удаленного доступа обратного прокси-сервера</p></td>
</tr>
<tr class="even">
<td><p>Внутренний DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Директор</p></td>
<td><p>Опубликованные веб-службы собраний обратного прокси-сервера</p></td>
</tr>
<tr class="odd">
<td><p>Внутренний DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Директор</p></td>
<td><p>Опубликовано и определено внешними службами веб-билетов обратного прокси-сервера для директора</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

