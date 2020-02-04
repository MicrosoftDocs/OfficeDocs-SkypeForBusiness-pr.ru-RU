---
title: 'Lync Server 2013: планирование емкости для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efb1b928ce7b4bafbbff20ad31872fe12735fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Планирование емкости для группы ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-29_

<div id="sectionSection0" class="section">

В приведенной ниже таблице описана пользовательская модель группы ответа, которую можно использовать в качестве основы для планирования производственных мощностей.

<div>


> [!NOTE]  
> Значения приведены для звуковых файлов группы ответа со следующими характеристиками: 16-разрядный файл с расширением WAV и частотой 16 кГц в монофонической записи. Если вы используете другие форматы файлов, например Windows Media Audio (WMA), характеристики могут отличаться.



</div>

<div>


> [!IMPORTANT]  
> При планировании мощности аварийного восстановления для парных пулов необходимо учитывать, что каждый пул, входящий в состав парного пула, должен обрабатывать рабочие нагрузки всех групп ответа в обоих пулах.



</div>

### <a name="response-group-user-model"></a>Пользовательская модель группы ответа

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Показатель</th>
<th>Пул корпоративных выпусков (с 8 серверами переднего плана)</th>
<th>Для каждого сервера Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Входящих звонков в секунду</p></td>
<td><p>шестнадцат</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Число звонков, одновременно подключенных к интерактивному автоответчику или находящихся на удержании</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Число одновременных анонимных сеансов (без учета сеансов обмена мгновенными сообщениями)</p></td>
<td><p>224</p></td>
<td><p>Плот</p></td>
</tr>
<tr class="even">
<td><p>Число одновременных анонимных сеансов (с учетом сеансов обмена мгновенными сообщениями)</p></td>
<td><p>64</p></td>
<td><p>No8</p></td>
</tr>
<tr class="odd">
<td><p>Число активных агентов (официальные и неофициальные)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Число сервисных групп</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Число групп интерактивного автоответчика (распознавание речи)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

