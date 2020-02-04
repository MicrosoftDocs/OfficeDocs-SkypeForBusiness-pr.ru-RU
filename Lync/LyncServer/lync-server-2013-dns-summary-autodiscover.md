---
title: 'Lync Server 2013: сводка DNS — автообнаружение'
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
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Сводка DNS: обнаружение автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-13_

Автообнаружение — это гибкая служба, в которой она будет поддерживать связь по протоколу HTTP или HTTPS. Для этого необходимо правильно настроить систему доменных имен (DNS) и сертификаты, используемые серверами, на которых размещается служба автообнаружения. Требования к сертификатам описаны в статье [сведения о сертификате: обнаружение автообнаружения в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> Логика поиска DNS для клиентов Lync Server использует определенную последовательность разрешения. Всегда следует включать и линкдисковеринтернал. &lt;Domain&gt; и lyncdiscover. &lt;домен&gt; в DNS. Исключение линкдисковеринтернал. &lt;запись&gt; домена приведет к тому, что внутренние клиенты не смогут подключиться к нужным службам или получить неправильный ответ автообнаружения.



</div>

### <a name="internal-dns-records"></a>Внутренние DNS-записи

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
<td><p>Линкдисковеринтернал. &lt;внутреннее доменное имя&gt;</p></td>
<td><p>Полное доменное имя веб-служб для пула, если у вас есть один из них или для пула переднего плана, если у вас нет директора.</p></td>
</tr>
<tr class="even">
<td><p>A (узел, если IPv6, AAAA)</p></td>
<td><p>линкдисковеринтернал. &lt;внутреннее доменное имя&gt;</p></td>
<td><p>Внутренний IP-адрес веб-служб (виртуальный IP-адрес), если вы используете подсистему балансировки нагрузки из вашего пула, если у вас нет директора.</p></td>
</tr>
</tbody>
</table>


Вам необходимо создать одну из следующих внешних DNS-записей:

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
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>Внешнее полное доменное имя веб-служб для пула, если у вас есть один из них или для пула переднего плана, если у вас нет директора.</p></td>
</tr>
<tr class="even">
<td><p>A (узел, если IPv6, AAAA)</p></td>
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>Внешний или общий IP-адрес обратного прокси-сервера.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Внешний трафик проходит через обратный прокси-сервер.



</div>

<div>


> [!NOTE]  
> Клиенты мобильных устройств не поддерживают несколько сертификатов SSL (Secure Sockets Layer) из разных доменов. Таким образом, перенаправление CNAME на разные домены не поддерживается по протоколу HTTPS. Например, запись DNS CNAME для lyncdiscover.contoso.com, которая перенаправляет адрес director.contoso.net, не поддерживается по протоколу HTTPS. В такой топологии клиенту на мобильном устройстве необходимо использовать HTTP для первого запроса, чтобы перенаправление CNAME было разрешено через HTTP. Затем последующие запросы используют протокол HTTPS. Для поддержки этого сценария необходимо настроить обратный прокси с помощью правила веб-публикации для порта 80 (HTTP). Дополнительные сведения можно найти в разделе "Создание правила веб-публикации для порта 80" при <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">настройке обратного прокси-сервера для мобильных устройств в Lync Server 2013</A>. Перенаправление CNAME на тот же домен поддерживается по протоколу HTTPS. В этом случае сертификат конечного домена охватывает исходный домен.



</div>

<div>

## <a name="see-also"></a>См. также


[Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Сведения о сертификате: обнаружение автообнаружения в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

