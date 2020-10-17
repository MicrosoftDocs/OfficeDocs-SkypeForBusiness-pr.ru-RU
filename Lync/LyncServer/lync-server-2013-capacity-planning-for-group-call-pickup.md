---
title: 'Lync Server 2013: планирование мощности при отправке звонков по группам'
description: 'Lync Server 2013: планирование мощности при отправке звонков по группам.'
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
ms.openlocfilehash: 12648c57d1036a0ed27c60ef6399bf570c5dcd3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544535"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="a2c86-103">Планирование емкости для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2c86-103">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2c86-104">_**Последнее изменение темы:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="a2c86-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="a2c86-105">В следующей таблице описывается пользовательская модель ответа на групповые звонки, которую можно использовать в качестве основы для требований по планированию мощности.</span><span class="sxs-lookup"><span data-stu-id="a2c86-105">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a2c86-106">Группа ответа на звонки основана на приложении парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="a2c86-106">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="a2c86-107">Имейте в виду, что при планировании мощности аварийного восстановления каждый пул в связанном пуле должен иметь возможность обрабатывать рабочие нагрузки для служб парковки вызовов, в том числе группового ответа на звонки в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="a2c86-107">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="a2c86-108">Пользовательская модель ответа на групповые звонки</span><span class="sxs-lookup"><span data-stu-id="a2c86-108">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2c86-109">Метрика</span><span class="sxs-lookup"><span data-stu-id="a2c86-109">Metric</span></span></th>
<th><span data-ttu-id="a2c86-110">На интерфейсный пул (с 8 серверами переднего плана)</span><span class="sxs-lookup"><span data-stu-id="a2c86-110">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="a2c86-111">Для каждого сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a2c86-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2c86-112">Рекомендованное количество пользователей в группе</span><span class="sxs-lookup"><span data-stu-id="a2c86-112">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="a2c86-113">50</span><span class="sxs-lookup"><span data-stu-id="a2c86-113">50</span></span></p></td>
<td><p><span data-ttu-id="a2c86-114">50</span><span class="sxs-lookup"><span data-stu-id="a2c86-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c86-115">Рекомендуемое количество групп</span><span class="sxs-lookup"><span data-stu-id="a2c86-115">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="a2c86-116">500</span><span class="sxs-lookup"><span data-stu-id="a2c86-116">500</span></span></p></td>
<td><p><span data-ttu-id="a2c86-117">60</span><span class="sxs-lookup"><span data-stu-id="a2c86-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c86-118">Максимальное число пользователей на пул, разрешенное для групповой отправки звонков</span><span class="sxs-lookup"><span data-stu-id="a2c86-118">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="a2c86-119">25 000 </span><span class="sxs-lookup"><span data-stu-id="a2c86-119">25,000</span></span></p></td>
<td><p><span data-ttu-id="a2c86-120">3,000</span><span class="sxs-lookup"><span data-stu-id="a2c86-120">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c86-121">Максимальная частота входящих вызовов для всех пользователей, для которых разрешено групповое получение вызовов для каждого пула в минуту</span><span class="sxs-lookup"><span data-stu-id="a2c86-121">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="a2c86-122">500</span><span class="sxs-lookup"><span data-stu-id="a2c86-122">500</span></span></p></td>
<td><p><span data-ttu-id="a2c86-123">60</span><span class="sxs-lookup"><span data-stu-id="a2c86-123">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c86-124">Максимальная частота вызовов, полученных пользователями с запросом группового ответа на пул в минуту</span><span class="sxs-lookup"><span data-stu-id="a2c86-124">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="a2c86-125">200</span><span class="sxs-lookup"><span data-stu-id="a2c86-125">200</span></span></p></td>
<td><p><span data-ttu-id="a2c86-126">25</span><span class="sxs-lookup"><span data-stu-id="a2c86-126">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="a2c86-127">Для интерфейсных пулов, в которых менее восьми серверов переднего плана, рассчитывайте метрики линейно.</span><span class="sxs-lookup"><span data-stu-id="a2c86-127">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="a2c86-128">Например, если в пуле переднего плана есть один сервер переднего плана, то необходимо рассчитать максимальную нагрузку, как 1/8 значений, показанных в таблице.</span><span class="sxs-lookup"><span data-stu-id="a2c86-128">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="a2c86-129">Вы можете увеличить или уменьшить рекомендуемое количество пользователей в группе и число групп, пока не превышено максимальное число пользователей на пул.</span><span class="sxs-lookup"><span data-stu-id="a2c86-129">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="a2c86-130">Например, на сервере Standard Edition может быть 120 групп с 25 пользователями на группу, так как количество пользователей, включенных для отправки групп, по-прежнему находится в пределах максимальной модели пользователя (то есть 120 групп раз — 3 000 пользователей, для которых включена Групповая отправка звонков).</span><span class="sxs-lookup"><span data-stu-id="a2c86-130">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

