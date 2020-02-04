---
title: 'Lync Server 2013: требования к сертификатам для организации мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Требования к сертификатам для организации мобильной работы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-24_

Если вы разворачиваете мобильное устройство и поддерживаете автоматическое обнаружение для мобильных клиентов, необходимо включить некоторые записи альтернативных имен для субъектов в сертификаты для обеспечения защищенных подключений из мобильных клиентов.

Необходимо включить записи альтернативных имен для субъектов для автоматического обнаружения в следующих сертификатах:

  - Пул директоров

  - Пул переднего плана

  - Сертификат обратного прокси-сервера

В этом разделе описаны записи альтернативных имен субъектов, необходимые для сертификатов для автоматического обнаружения.

<div>


> [!NOTE]  
> Повторное выдача сертификатов с помощью внутреннего центра сертификации обычно является простым процессом, но добавление нескольких записей альтернативных имен субъектов в общедоступные сертификаты, используемые обратным прокси, может быть дорогостоящим. Если у вас много доменов SIP, что значительно затрудняет Добавление альтернативных имен субъектов, вы можете настроить обратный прокси так, чтобы он использовал HTTP для первоначального запроса на обслуживание автообнаружения, вместо использования HTTPS (конфигурация по умолчанию). Подробности можно найти <A href="lync-server-2013-technical-requirements-for-mobility.md">в разделе Технические требования для мобильных устройств на Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Требования к сертификатам пула директоров

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL-адрес внутренней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;домен_SIP&gt;</p></td>
</tr>
<tr class="even">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.&lt;домен_SIP&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Кроме того, вы можете использовать сеть SAN = *. &lt;сипдомаин&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Требования к сертификату пула переднего плана

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL-адрес внутренней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;домен_SIP&gt;</p></td>
</tr>
<tr class="even">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.&lt;домен_SIP&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Кроме того, вы можете использовать сеть SAN = *. &lt;сипдомаин&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Требования сертификата по обратному прокси (общедоступному центру сертификации)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.&lt;домен_SIP&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Вы назначаете эту сеть SAN сертификату, назначенному прослушивателю SSL на обратном прокси-сервере.



</div>

<div>


> [!NOTE]  
> В обратном прослушивателе прокси-сервера будут указаны альтернативные имена для URL-адресов внешних веб-служб (например, SAN = lyncwebextpool01. contoso. com и dirwebexternal.contoso.com, если вы развернули дополнительный режиссер).



</div>

</div>

<span> </span>

</div>

</div>

</div>

