---
title: Исключения для Lync Server 2013 IPsec
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Исключения IPsec в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-27_

Для корпоративных сетей, где развернута безопасность протокола IP (IPsec) (ознакомьтесь со статьей IETF RFC 4301-4309), необходимо отключить IPsec для диапазона портов, используемых для доставки звуковых, видеофайлов и панорамных видео. Согласно рекомендациям, необходимо избегать задержек при выделении портов носителей из-за согласования IPsec.

В приведенной ниже таблице описаны рекомендуемые параметры исключений IPsec.

### <a name="recommended-ipsec-exceptions"></a>Рекомендуемые исключения IPsec

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя правила</th>
<th>Исходный IP-адрес</th>
<th>Конечный IP-адрес</th>
<th>Протокол</th>
<th>Исходный порт</th>
<th>Конечный порт</th>
<th>Требование для проверки подлинности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренний Входящий сервер пограничного сервера/V</p></td>
<td><p>Любой</p></td>
<td><p>Внутренний сервер пограничного сервера/V</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="even">
<td><p>Внешний Входящий сервер пограничного сервера/V</p></td>
<td><p>Любой</p></td>
<td><p>Внешний сервер пограничного сервера/V</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Внутренний исходящий сервер пограничного сервера/V</p></td>
<td><p>Внутренний сервер пограничного сервера/V</p></td>
<td><p>Любой</p></td>
<td><p>UDP &amp; -TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="even">
<td><p>Внешний исходящий сервер пограничного сервера/V</p></td>
<td><p>Внешний сервер пограничного сервера/V</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящее на сервер обновлений</p></td>
<td><p>Любой</p></td>
<td><p>Посредник</p>
<p>Сервер (-ы)</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие запросы сервера исправлений</p></td>
<td><p>Посредник</p>
<p>Сервер (-ы)</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящее участие в конференциях</p></td>
<td><p>Любой</p></td>
<td><p>Сервер переднего плана с запущенным помощником по конференциям</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие участники конференц-связи</p></td>
<td><p>Сервер переднего плана с запущенным помощником по конференциям</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящее видеоконференции/V</p></td>
<td><p>Любой</p></td>
<td><p>переднего плана</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие подключения к конференциям/V</p></td>
<td><p>переднего плана</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящее на Exchange</p></td>
<td><p>Любой</p></td>
<td><p>Единая система обмена сообщениями Exchange</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="even">
<td><p>Серверы общего обмена приложениями, входящие</p></td>
<td><p>Любой</p></td>
<td><p>Серверы общего обмена приложениями</p></td>
<td><p>TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Исходящие запросы сервера общего приложения</p></td>
<td><p>Серверы общего обмена приложениями</p></td>
<td><p>Любой</p></td>
<td><p>TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие сообщения Exchange</p></td>
<td><p>Единая система обмена сообщениями Exchange</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Клиенты</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>UDP</p></td>
<td><p>Указанный диапазон портов мультимедиа</p></td>
<td><p>Любой</p></td>
<td><p>Без проверки подлинности</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

