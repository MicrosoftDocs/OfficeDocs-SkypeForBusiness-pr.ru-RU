---
title: Сводка по сертификатам — масштабируемый пул директоров, аппаратный балансировщик нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c08fb5710e25bf4504d7cb2d10020138221b22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507926"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Сводка по сертификатам — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

Требования к сертификатам для директора с аппаратной подсистемой балансировки нагрузки будут использовать сертификат по умолчанию с именем субъекта и альтернативными именами субъектов для служб, которые может получить пул директоров. Для каждого директора в пуле запрашивается сертификат. Кроме того, существует сертификат маркера OAuth для проверки подлинности сервера на сервере, установленный на каждом сервере.

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>Сертификаты для масштабируемого директора с использованием аппаратного балансировщика нагрузки

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
<th>Имя субъекта</th>
<th>Альтернативные имена субъектов</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>По умолчанию</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Дополнительно) *.contoso.com</p></td>
<td><p>Сертификаты директора могут запрашиваться как из внутреннего управляемого центра сертификации, так и из общедоступного центра сертификации.</p>
<p>Режиссер отвечает на запросы от обратного прокси-сервера в сети периметра или от пограничного сервера.</p>
<p>Или запись с подстановочными знаками для простых URL-адресов</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Без записи</p></td>
<td>


> [!IMPORTANT]
> Обратите внимание, что минимальная длина ключа равна 1024, однако может возникнуть предупреждение, что рекомендуемая минимальная длина равна 2048 битам.


<p>Сертификат OAuthTokenIssuer — это специализированный сертификат для проверки подлинности серверов в крупномасштабной среде, который можно запросить из внутреннего или из общего центра сертификации. Этот сертификат является обязательным.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

