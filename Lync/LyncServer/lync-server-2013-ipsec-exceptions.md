---
title: Исключения для Lync Server 2013 IPsec
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733459"
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

Для корпоративных сетей, где развернута безопасность протокола IP (IPsec) (ознакомьтесь со статьей IETF RFC 4301-4309), необходимо отключить IPsec для диапазона портов, используемых для доставки звуковых, видеофайлов и панорамных видео. Это связано с необходимостью избежать каких-либо задержек при распределении портов мультимедиа из-за согласования IPsec.

В следующей таблице описаны рекомендуемые исключения IPsec.

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
<th>Требование проверки подлинности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренние входящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>Внутренние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Внешние входящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>Внешние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Внутренние исходящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Внутренние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Внешние исходящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Внешние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные сервера-посредника</p></td>
<td><p>Любой</p></td>
<td><p>Серверы-</p>
<p>посредники</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные сервера-посредника</p></td>
<td><p>Серверы-</p>
<p>посредники</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные помощника по конференц-связи</p></td>
<td><p>Любой</p></td>
<td><p>Сервер переднего плана с помощником по конференц-связи</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные помощника по конференц-связи</p></td>
<td><p>Сервер переднего плана с помощником по конференц-связи</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные аудио- и видеоконференций</p></td>
<td><p>Любой</p></td>
<td><p>Серверы переднего плана</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные аудио- и видеоконференций</p></td>
<td><p>Серверы переднего плана</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные Exchange</p></td>
<td><p>Любой</p></td>
<td><p>Единая система обмена сообщениями Exchange</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Входящие данные серверов совместного использования приложений</p></td>
<td><p>Любой</p></td>
<td><p>Серверы совместного использования приложений</p></td>
<td><p>TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Исходящие данные серверов совместного использования приложений</p></td>
<td><p>Серверы совместного использования приложений</p></td>
<td><p>Любой</p></td>
<td><p>TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные Exchange</p></td>
<td><p>Единая система обмена сообщениями Exchange</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Клиенты</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>UDP</p></td>
<td><p>Указанный диапазон портов мультимедиа</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

