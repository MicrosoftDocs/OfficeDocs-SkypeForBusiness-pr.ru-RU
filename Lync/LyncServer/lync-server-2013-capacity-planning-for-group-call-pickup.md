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
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512816"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="d1db6-102">Планирование емкости для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1db6-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1db6-103">_**Последнее изменение темы:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="d1db6-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="d1db6-104">В следующей таблице описывается пользовательская модель ответа на групповые звонки, которую можно использовать в качестве основы для требований по планированию мощности.</span><span class="sxs-lookup"><span data-stu-id="d1db6-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1db6-105">Группа ответа на звонки основана на приложении парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="d1db6-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="d1db6-106">Имейте в виду, что при планировании мощности аварийного восстановления каждый пул в связанном пуле должен иметь возможность обрабатывать рабочие нагрузки для служб парковки вызовов, в том числе группового ответа на звонки в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="d1db6-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="d1db6-107">Пользовательская модель ответа на групповые звонки</span><span class="sxs-lookup"><span data-stu-id="d1db6-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1db6-108">Метрика</span><span class="sxs-lookup"><span data-stu-id="d1db6-108">Metric</span></span></th>
<th><span data-ttu-id="d1db6-109">На интерфейсный пул (с 8 серверами переднего плана)</span><span class="sxs-lookup"><span data-stu-id="d1db6-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="d1db6-110">Для каждого сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d1db6-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1db6-111">Рекомендованное количество пользователей в группе</span><span class="sxs-lookup"><span data-stu-id="d1db6-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="d1db6-112">50</span><span class="sxs-lookup"><span data-stu-id="d1db6-112">50</span></span></p></td>
<td><p><span data-ttu-id="d1db6-113">50</span><span class="sxs-lookup"><span data-stu-id="d1db6-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1db6-114">Рекомендуемое количество групп</span><span class="sxs-lookup"><span data-stu-id="d1db6-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="d1db6-115">500</span><span class="sxs-lookup"><span data-stu-id="d1db6-115">500</span></span></p></td>
<td><p><span data-ttu-id="d1db6-116">60</span><span class="sxs-lookup"><span data-stu-id="d1db6-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1db6-117">Максимальное число пользователей на пул, разрешенное для групповой отправки звонков</span><span class="sxs-lookup"><span data-stu-id="d1db6-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="d1db6-118">25 000 </span><span class="sxs-lookup"><span data-stu-id="d1db6-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="d1db6-119">3,000</span><span class="sxs-lookup"><span data-stu-id="d1db6-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1db6-120">Максимальная частота входящих вызовов для всех пользователей, для которых разрешено групповое получение вызовов для каждого пула в минуту</span><span class="sxs-lookup"><span data-stu-id="d1db6-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="d1db6-121">500</span><span class="sxs-lookup"><span data-stu-id="d1db6-121">500</span></span></p></td>
<td><p><span data-ttu-id="d1db6-122">60</span><span class="sxs-lookup"><span data-stu-id="d1db6-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1db6-123">Максимальная частота вызовов, полученных пользователями с запросом группового ответа на пул в минуту</span><span class="sxs-lookup"><span data-stu-id="d1db6-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="d1db6-124">200</span><span class="sxs-lookup"><span data-stu-id="d1db6-124">200</span></span></p></td>
<td><p><span data-ttu-id="d1db6-125">25</span><span class="sxs-lookup"><span data-stu-id="d1db6-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="d1db6-126">Для интерфейсных пулов, в которых менее восьми серверов переднего плана, рассчитывайте метрики линейно.</span><span class="sxs-lookup"><span data-stu-id="d1db6-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="d1db6-127">Например, если в пуле переднего плана есть один сервер переднего плана, то необходимо рассчитать максимальную нагрузку, как 1/8 значений, показанных в таблице.</span><span class="sxs-lookup"><span data-stu-id="d1db6-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="d1db6-128">Вы можете увеличить или уменьшить рекомендуемое количество пользователей в группе и число групп, пока не превышено максимальное число пользователей на пул.</span><span class="sxs-lookup"><span data-stu-id="d1db6-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="d1db6-129">Например, на сервере Standard Edition может быть 120 групп с 25 пользователями на группу, так как количество пользователей, включенных для отправки групп, по-прежнему находится в пределах максимальной модели пользователя (то есть 120 групп раз — 3 000 пользователей, для которых включена Групповая отправка звонков).</span><span class="sxs-lookup"><span data-stu-id="d1db6-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

