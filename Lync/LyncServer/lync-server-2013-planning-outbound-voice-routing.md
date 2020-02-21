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
ms.openlocfilehash: a2fd202d6526f1f093c5824944ffdf3aa58317a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="96235-102">Планирование маршрутизации исходящих голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96235-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96235-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="96235-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="96235-p101">Маршрутизация исходящих вызовов относится к вызовам, предназначенным для шлюза ТСОП, магистральной линии или офисной АТС. Когда пользователь размещает вызов, сервер при необходимости преобразует телефонный номер в формат E.164 и пытается сопоставить его с SIP URI. Если сопоставление не удается, то сервер применяет логику маршрутизации исходящих вызовов на основе представленной строки набора. Эта логика задается путем настройки параметров сервера, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="96235-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="96235-108">Параметры маршрутизации исходящих вызовов Lync Server</span><span class="sxs-lookup"><span data-stu-id="96235-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96235-109">Объект</span><span class="sxs-lookup"><span data-stu-id="96235-109">Object</span></span></th>
<th><span data-ttu-id="96235-110">Описание</span><span class="sxs-lookup"><span data-stu-id="96235-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96235-111">Абонентская группа</span><span class="sxs-lookup"><span data-stu-id="96235-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="96235-112">Абонентская группа — это именованный набор правил нормализации, преобразующих телефонные номера для указанного расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для авторизации телефона и маршрутизации вызова.</span><span class="sxs-lookup"><span data-stu-id="96235-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96235-113">Правило нормализации</span><span class="sxs-lookup"><span data-stu-id="96235-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="96235-p102">Правила нормализации указывают, как телефонные номера, выраженные в разных форматах, должны маршрутизироваться для каждого конкретного расположения, пользователя или контактного объекта. Одна и та же строка набора может интерпретироваться и преобразовываться по-разному, в зависимости от местоположения, из которого она была набрана, и лица или контактного объекта, выполнившего вызов. Ряд правил нормализации, связанный с конкретным расположением, составляет абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="96235-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96235-117">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="96235-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="96235-p103">Политика голосовой связи связывает одну или несколько записей режима работы с ТСОП с одним пользователем или группой пользователей. Политика голосовой связи также предоставляет список функций вызовов, которые можно включать или отключать.</span><span class="sxs-lookup"><span data-stu-id="96235-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96235-120">Запись режима работы с ТСОП</span><span class="sxs-lookup"><span data-stu-id="96235-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="96235-121">Запись режима работы с ТСОП задает класс вызовов (например, внутренний, местный или междугородный), которые могут выполняться разными пользователями или группами пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="96235-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96235-122">Маршрут вызова</span><span class="sxs-lookup"><span data-stu-id="96235-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="96235-p104">Маршрут вызова связывает телефонные номера назначения с конкретными каналами и записями режимов работы с ТСОП. Шлюз ТСОП рассматривается как канал.</span><span class="sxs-lookup"><span data-stu-id="96235-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="96235-125">Содержание</span><span class="sxs-lookup"><span data-stu-id="96235-125">In This Section</span></span>

<span data-ttu-id="96235-126">В этом разделе предоставляются рекомендации по настройке следующих параметров сервера маршрутизации исходящих вызовов:</span><span class="sxs-lookup"><span data-stu-id="96235-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="96235-127">Абонентские группы и правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96235-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="96235-128">Политики голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96235-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="96235-129">Записи использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96235-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="96235-130">Маршруты голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96235-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96235-131">См. также</span><span class="sxs-lookup"><span data-stu-id="96235-131">See Also</span></span>


[<span data-ttu-id="96235-132">Распределение каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96235-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="96235-133">Прямые подключения SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96235-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

