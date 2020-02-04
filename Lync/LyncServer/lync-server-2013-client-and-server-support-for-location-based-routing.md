---
title: 'Lync Server 2013: поддержка маршрутизации на основе расположения клиентами и серверами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Поддержка маршрутизации на основе расположения клиентами и серверами в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-06-18_

Маршрутизация на основе местоположения обеспечивается приложением Lync Server. Lync Server может определять сетевые сайты, в которых пользователи подключаются из корпоративной сети. Расположение удаленных пользователей считается неизвестным, поскольку они находятся вне корпоративной сети.

<div>

## <a name="lync-server-support"></a>Поддержка Lync Server

Для маршрутизации на основе местоположения требуется, чтобы Lync Server 2013 CU1 был развернут на всех пулах интерфейсных и стандартных серверах выпуска в заданной топологии. Если Lync Server 2013 CU1 не установлен в некоторых компонентах Lync в топологии, ограничения на маршрутизацию с учетом расположения не могут быть полностью применены.

В следующей таблице указаны комбинации ролей сервера и версий, которые поддерживаются для маршрутизации на основе местоположения.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Версия пула</th>
<th>Версия cервера-посредника</th>
<th>Поддерживается</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Накопительное обновление для Lync Server 2013 за Февраль 2013</p></td>
<td><p>Накопительное обновление для Lync Server 2013 за Февраль 2013</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Накопительное обновление для Lync Server 2013 за Февраль 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>нет</p></td>
</tr>
<tr class="odd">
<td><p>Накопительное обновление для Lync Server 2013 за Февраль 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>нет</p></td>
</tr>
<tr class="even">
<td><p>Накопительное обновление для Lync Server 2013 за Февраль 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>нет</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>любая</p></td>
<td><p>нет</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>любая</p></td>
<td><p>нет</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>любая</p></td>
<td><p>нет</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Поддержка клиента Lync

В следующей таблице указаны клиенты, которые поддерживают маршрутизацию с учетом расположения.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип клиента</th>
<th>Поддерживается</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Да</p></td>
<td><p>В том числе накопительное обновление для Lync 2013 за Февраль 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>нет</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync для Windows 8</p></td>
<td><p>нет</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>нет</p></td>
<td><p>Для клиентов Lync Mobile 2013 необходимо отключить VoIP, если они используются пользователями, для которых включена маршрутизация на основе местоположения.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Чтобы отключить VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с параметром, IP аудио-и видеофайлы, отключенными для всех пользователей, для которых включена маршрутизация на основе местоположения. Более подробно о политике мобильности см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

