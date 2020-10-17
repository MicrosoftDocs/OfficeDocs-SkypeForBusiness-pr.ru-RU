---
title: 'Lync Server 2013: поддержка маршрутизации Location-Based на клиенте и сервере'
description: 'Lync Server 2013: поддержка маршрутизации Location-Based клиентом и сервером.'
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
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549635"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Поддержка маршрутизации Location-Based для клиентов и серверов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-06-18_

Location-Based маршрутизация обеспечивается Lync Server. Lync Server может определять сетевые сайты, к которым пользователи подключаются из корпоративной сети. Так как удаленные пользователи выходят за границы корпоративной сети, их расположение считается неизвестным.

<div>

## <a name="lync-server-support"></a>Поддержка Lync Server

Для маршрутизации Location-Based необходимо, чтобы Lync Server 2013 CU1 был развернут на всех интерфейсных пулах и серверах Standard Edition в заданной топологии. Если Lync Server 2013 CU1 не установлен на определенных компонентах Lync в топологии, ограничения маршрутизации Location-Based не могут быть полностью применены.

В следующей таблице указаны комбинации ролей и версий сервера, которые поддерживаются для маршрутизации Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Версия пула</th>
<th>Версия сервера-посредника</th>
<th>Поддерживается</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Накопительный пакет обновления Lync Server 2013 февраль 2013</p></td>
<td><p>Накопительный пакет обновления Lync Server 2013 февраль 2013</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Накопительный пакет обновления Lync Server 2013 февраль 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Накопительный пакет обновления Lync Server 2013 февраль 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Накопительный пакет обновления Lync Server 2013 февраль 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>любой</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>любой</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>любой</p></td>
<td><p>Нет</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Поддержка клиента Lync

В следующей таблице указаны клиенты, которые Location-Based поддерживаются службой маршрутизации.


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
<td><p>В том числе Lync 2013 февраль 2013 накопительный пакет обновления</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Нет</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Помощник по Lync</p></td>
<td><p>Да</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync для Windows 8</p></td>
<td><p>Нет</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>Нет</p></td>
<td><p>Службу VoIP необходимо отключить для клиентов Lync Mobile 2013, если они используются пользователями с включенной маршрутизацией Location-Based.</p></td>
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
> Чтобы отключить VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с параметром, IP-аудио/видео, отключенным для всех пользователей, для которых включена маршрутизация на основе расположения. Дополнительные сведения о политике мобильности можно найти в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New – CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование маршрутизации Location-Based в Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

