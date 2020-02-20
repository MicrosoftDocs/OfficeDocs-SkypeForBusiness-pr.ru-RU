---
title: 'Lync Server 2013: планирование маршрутизации исходящих голосовых вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e912a3934ae7262c85cfb7b47c62abf6bc70b5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Планирование маршрутизации исходящих голосовых вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Маршрутизация исходящих вызовов относится к вызовам, предназначенным для шлюза ТСОП, магистральной линии или офисной АТС. Когда пользователь размещает вызов, сервер при необходимости преобразует телефонный номер в формат E.164 и пытается сопоставить его с SIP URI. Если сопоставление не удается, то сервер применяет логику маршрутизации исходящих вызовов на основе представленной строки набора. Эта логика задается путем настройки параметров сервера, описанных в следующей таблице.

### <a name="lync-server-outbound-call-routing-settings"></a>Параметры маршрутизации исходящих вызовов Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Объект</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Абонентская группа</p></td>
<td><p>Абонентская группа — это именованный набор правил нормализации, преобразующих телефонные номера для указанного расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для авторизации телефона и маршрутизации вызова.</p></td>
</tr>
<tr class="even">
<td><p>Правило нормализации</p></td>
<td><p>Правила нормализации указывают, как телефонные номера, выраженные в разных форматах, должны маршрутизироваться для каждого конкретного расположения, пользователя или контактного объекта. Одна и та же строка набора может интерпретироваться и преобразовываться по-разному, в зависимости от местоположения, из которого она была набрана, и лица или контактного объекта, выполнившего вызов. Ряд правил нормализации, связанный с конкретным расположением, составляет абонентскую группу.</p></td>
</tr>
<tr class="odd">
<td><p>Политика голосовой связи</p></td>
<td><p>Политика голосовой связи связывает одну или несколько записей режима работы с ТСОП с одним пользователем или группой пользователей. Политика голосовой связи также предоставляет список функций вызовов, которые можно включать или отключать.</p></td>
</tr>
<tr class="even">
<td><p>Запись режима работы с ТСОП</p></td>
<td><p>Запись режима работы с ТСОП задает класс вызовов (например, внутренний, местный или междугородный), которые могут выполняться разными пользователями или группами пользователей в организации.</p></td>
</tr>
<tr class="odd">
<td><p>Маршрут вызова</p></td>
<td><p>Маршрут вызова связывает телефонные номера назначения с конкретными каналами и записями режимов работы с ТСОП. Шлюз ТСОП рассматривается как канал.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Содержание

В этом разделе предоставляются рекомендации по настройке следующих параметров сервера маршрутизации исходящих вызовов:

  - <span></span>  
    [Абонентские группы и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Политики голосовой связи в Lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Записи использования PSTN в Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Маршруты голосовой связи в Lync Server 2013](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Распределение каналов SIP в Lync Server 2013](lync-server-2013-sip-trunking.md)  
[Прямые подключения SIP в Lync Server 2013](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

