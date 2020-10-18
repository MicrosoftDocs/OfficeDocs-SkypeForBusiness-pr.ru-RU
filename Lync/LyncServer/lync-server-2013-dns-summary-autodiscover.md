---
title: 'Lync Server 2013: сводка по DNS — автообнаружение'
description: 'Lync Server 2013: сводка по DNS — автообнаружение.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574285"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Сводка по DNS — автообнаружение в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-13_

Автообнаружение — это гибкая служба, в которой она будет принимать связь по протоколу HTTP или HTTPS. Для этого необходимо правильно настроить систему доменных имен (DNS) и сертификаты, используемые серверами, на которых размещается служба автообнаружения. Требования к сертификатам описаны в разделе [сведения о сертификатах — автообнаружение в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> Логика поиска DNS для клиентов Lync Server использует определенный порядок разрешения. Всегда следует включать как lyncdiscoverinternal. &lt; Domain &gt; и lyncdiscover. &lt; домен &gt; в службе DNS. Исключение lyncdiscoverinternal. &lt; в &gt; результате записи домена внутренние клиенты не смогут подключаться к необходимым службам или получать неверный ответ автообнаружения.



</div>

### <a name="internal-dns-records"></a>Внутренние записи DNS

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип записи</th>
<th>Имя узла</th>
<th>Разрешается в</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt; внутреннее доменное имя&gt;</p></td>
<td><p>Полное доменное имя внутренних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора.</p></td>
</tr>
<tr class="even">
<td><p>A (узел, если используется IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt; внутреннее доменное имя&gt;</p></td>
<td><p>IP-адрес внутренних веб-служб (виртуальный IP-адрес), если вы используете подсистему балансировки нагрузки для пула директоров (если у вас есть один или из интерфейсного пула, если у вас нет директора).</p></td>
</tr>
</tbody>
</table>


Необходимо создать одну из следующих внешних DNS-записей:

### <a name="external-dns-records"></a>Внешние записи DNS

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип записи</th>
<th>Имя узла</th>
<th>Разрешается в</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>Полное доменное имя внешних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора.</p></td>
</tr>
<tr class="even">
<td><p>A (узел, если используется IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>Внешний или общедоступный IP-адрес обратного прокси-сервера.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Внешний трафик проходит через обратный прокси-сервер.



</div>

<div>


> [!NOTE]  
> Клиенты мобильных устройств не поддерживают множество сертификатов SSL из разных доменов. Поэтому перенаправление CNAME в различные домены по протоколу HTTPS не поддерживается. Например, запись DNS CNAME для домена lyncdiscover.contoso.com, которая выполняет перенаправление на адрес director.contoso.net, не поддерживается по протоколу HTTPS. В такой топологии клиент мобильного устройства должен использовать HTTP для первого запроса, чтобы перенаправление CNAME разрешалось по протоколу HTTP. Последующие запросы могут использовать HTTPS. Для поддержки этого сценария необходимо настроить обратный прокси-сервер с использованием правила веб-публикации для порта 80 (HTTP). Сведения о том, как создать правило веб-публикации для порта 80 "в разделе <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</A>. Перенаправление CNAME в тот же домен поддерживается по протоколу HTTPS. В этом случае сертификат конечного домена охватывает исходный домен.



</div>

<div>

## <a name="see-also"></a>См. также


[Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Сводка по сертификатам — автообнаружение в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

