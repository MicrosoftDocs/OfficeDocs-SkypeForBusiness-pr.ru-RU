---
title: 'Lync Server 2013: сводка по сертификатам — единственный директор'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a>Сводка по сертификатам — единственный директор в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-08_

Требования к сертификатам для единого директора состоят из сертификата по умолчанию, который содержит имя субъекта и другие имена тем для служб, которые может получать руководитель. Кроме того, существует сертификат маркера OAuth для проверки подлинности сервера и сервера.

### <a name="certificates-for-director"></a>Сертификаты для режиссера

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Компонент</th>
<th>Имя субъекта (SN)</th>
<th>Дополнительные имена субъектов (SAN)</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>"Default" (По умолчанию)</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Необязательно) *. contoso.com</p></td>
<td><p>Сертификаты в службе каталогов могут запрашиваться либо с помощью внутреннего управляемого центра сертификации (ЦС), либо из общедоступного центра сертификации.</p>
<p>Режиссер отвечает на запросы на обратных прокси-серверах периметра или пограничного сервера. Внутренние клиенты не будут использовать режиссер.</p>
<p>Или подстановочный знак для простых URL-адресов</p></td>
</tr>
<tr class="even">
<td><p>оаустокениссуер</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Нет записи</p></td>
<td><div>

> [!IMPORTANT]  
> Обратите внимание, что минимальная длина ключа составляет 1024, но вы можете получить предупреждение о том, что минимальная рекомендуемая длина ключа составляет 2048 бит.


</div>
<p>Сертификат Оаустокениссуер является однозначным сертификатом для серверов с проверкой подлинности в крупномасштабной среде и может запрашиваться из внутреннего или общедоступного ЦС. Требуется сертификат.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

