---
title: Сводка по сертификатам — масштабированный пул директоров, аппаратный балансировщик нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b1688641d09e00c82ea952d57bd2a9547ac0dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Сводка по сертификатам — масштабированный пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Требования к сертификатам для режиссера с помощью аппаратной подсистемы балансировки нагрузки будут использовать сертификат по умолчанию, который содержит имя субъекта и альтернативные имена субъектов для служб, которые может получать пул режиссера. Для каждого режиссера в пуле запрашивается сертификат. Кроме того, существует сертификат маркеров OAuth для проверки подлинности сервера и сервера, установленный на каждом сервере.

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>Сертификаты для масштабированного директора с помощью аппаратной подсистемы балансировки нагрузки

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
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Необязательно) *. contoso.com</p></td>
<td><p>Сертификаты в службе каталогов могут запрашиваться либо с помощью внутреннего управляемого центра сертификации (ЦС), либо из общедоступного центра сертификации.</p>
<p>Режиссер отвечает на запросы на обратных прокси-серверах периметра или пограничного сервера.</p>
<p>Или подстановочный знак для простых URL-адресов</p></td>
</tr>
<tr class="even">
<td><p>Оаустокениссуер</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Нет записи</p></td>
<td>


> [!IMPORTANT]
> Обратите внимание, что минимальная длина ключа составляет 1024, но вы можете получить предупреждение о том, что минимальная рекомендуемая длина ключа составляет 2048 бит.


<p>Сертификат Оаустокениссуер является однозначным сертификатом для серверов с проверкой подлинности в крупномасштабной среде и может запрашиваться из внутреннего или общедоступного ЦС. Требуется сертификат.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

