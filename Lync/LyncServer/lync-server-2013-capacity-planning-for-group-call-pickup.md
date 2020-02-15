---
title: 'Lync Server 2013: планирование мощности при отправке звонков по группам'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 403a00887cb64b33075f173499e855eb8783bb20
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Планирование емкости для группового ответа на звонки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-12_

<div id="sectionSection0" class="section">

В следующей таблице описывается пользовательская модель ответа на групповые звонки, которую можно использовать в качестве основы для требований по планированию мощности.

<div>


> [!IMPORTANT]  
> Группа ответа на звонки основана на приложении парковки вызовов. Имейте в виду, что при планировании мощности аварийного восстановления каждый пул в связанном пуле должен иметь возможность обрабатывать рабочие нагрузки для служб парковки вызовов, в том числе группового ответа на звонки в обоих пулах.



</div>

### <a name="group-call-pickup-user-model"></a>Пользовательская модель ответа на групповые звонки

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Метр</th>
<th>На интерфейсный пул (с 8 серверами переднего плана)</th>
<th>Для каждого сервера Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Рекомендованное количество пользователей в группе</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Рекомендуемое количество групп</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Максимальное число пользователей на пул, разрешенное для групповой отправки звонков</p></td>
<td><p>25 000 </p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>Максимальная частота входящих вызовов для всех пользователей, для которых разрешено групповое получение вызовов для каждого пула в минуту</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Максимальная частота вызовов, полученных пользователями с запросом группового ответа на пул в минуту</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Для интерфейсных пулов, в которых менее восьми серверов переднего плана, рассчитывайте метрики линейно. Например, если в пуле переднего плана есть один сервер переднего плана, то необходимо рассчитать максимальную нагрузку, как 1/8 значений, показанных в таблице.</P>
> <LI>
> <P>Вы можете увеличить или уменьшить рекомендуемое количество пользователей в группе и число групп, пока не превышено максимальное число пользователей на пул. Например, на сервере Standard Edition может быть 120 групп с 25 пользователями на группу, так как количество пользователей, включенных для отправки групп, по-прежнему находится в пределах максимальной модели пользователя (то есть 120 групп раз — 3 000 пользователей, для которых включена Групповая отправка звонков).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

