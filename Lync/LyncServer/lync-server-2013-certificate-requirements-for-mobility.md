---
title: 'Lync Server 2013: требования к сертификатам для мобильной работы'
description: 'Lync Server 2013: требования к сертификатам для мобильных устройств.'
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
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575205"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Требования к сертификатам для мобильных устройств в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-24_

При развертывании функции мобильной связи и поддержки автоматического обнаружения для мобильных клиентов потребуется добавить в сертификаты записи альтернативных имен субъектов для поддержки безопасных подключений мобильных клиентов.

Сертификаты, в которые необходимо добавить записи альтернативных имен субъектов для автоматического обнаружения:

  - Пул директоров

  - Интерфейсный пул

  - Сертификат обратного прокси-сервера

В этом разделе описываются записи альтернативных имен субъектов, которые требуется добавить в сертификаты для автоматического обнаружения.

<div>


> [!NOTE]  
> Обычно повторная выдача сертификатов с использованием внутреннего центра сертификации — это простой процесс, но добавление нескольких альтернативных имен субъектов в общедоступные сертификаты, используемые обратным прокси-сервером может быть ресурсоемкой задачей. Если у вас много доменов SIP, что делает добавление альтернативных имен субъектов очень дорогим, можно настроить обратный прокси для использования протокола HTTP для первоначального запроса службы автообнаружения вместо использования HTTPS (конфигурация по умолчанию). Дополнительные сведения см <A href="lync-server-2013-technical-requirements-for-mobility.md">в статье технические требования к мобильности в Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Требования к сертификатам пула Директор

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
<td><p>Внутренний URL-адрес службы автообнаружения</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Кроме того, вы можете использовать сеть SAN = *. &lt; sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Требования к сертификатам интерфейсного пула

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
<td><p>Внутренний URL-адрес службы автообнаружения</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>Внешний URL-адрес службы автообнаружения</p></td>
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Кроме того, вы можете использовать сеть SAN = *. &lt; sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Требования к сертификатам обратного прокси-сервера (общедоступного центра сертификации)

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
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Это альтернативное имя субъекта назначается сертификату, назначенному прослушивателю SSL на обратном прокси-сервере.



</div>

<div>


> [!NOTE]  
> Прослушиватель обратного прокси-сервера будет содержать альтернативные имена субъектов для URL-адресов внешних веб-служб (например, SAN = lyncwebextpool01. contoso. com и dirwebexternal.contoso.com, если вы развернули необязательный директор).



</div>

</div>

<span> </span>

</div>

</div>

</div>

