---
title: 'Lync Server 2013: планирование мощности для отправки группового звонка'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="98149-102">Планирование мощностей для отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98149-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98149-103">_**Тема последнего изменения:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="98149-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="98149-104">В приведенной ниже таблице описаны пользовательские модели отправки звонков групп, которые можно использовать в качестве основы для планирования производственных мощностей.</span><span class="sxs-lookup"><span data-stu-id="98149-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98149-105">Отправка группового звонка осуществляется на основе заявления на приостановку звонков.</span><span class="sxs-lookup"><span data-stu-id="98149-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="98149-106">Имейте в виду, что при планировании производительности аварийного восстановления каждый пул из сопряженного пула может обрабатывать рабочие нагрузки для служб приостановки звонков, в том числе для отправки группового звонка в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="98149-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="98149-107">Пользовательская модель отправки группового звонка</span><span class="sxs-lookup"><span data-stu-id="98149-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98149-108">Показатель</span><span class="sxs-lookup"><span data-stu-id="98149-108">Metric</span></span></th>
<th><span data-ttu-id="98149-109">На пул переднего плана (с 8 серверами переднего плана)</span><span class="sxs-lookup"><span data-stu-id="98149-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="98149-110">Для каждого сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="98149-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98149-111">Рекомендуемое число пользователей на группу</span><span class="sxs-lookup"><span data-stu-id="98149-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="98149-112">50</span><span class="sxs-lookup"><span data-stu-id="98149-112">50</span></span></p></td>
<td><p><span data-ttu-id="98149-113">50</span><span class="sxs-lookup"><span data-stu-id="98149-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98149-114">Рекомендуемое число групп</span><span class="sxs-lookup"><span data-stu-id="98149-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="98149-115">500</span><span class="sxs-lookup"><span data-stu-id="98149-115">500</span></span></p></td>
<td><p><span data-ttu-id="98149-116">60</span><span class="sxs-lookup"><span data-stu-id="98149-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98149-117">Максимальное число пользователей на пул, разрешенное для группового ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="98149-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="98149-118">25 000</span><span class="sxs-lookup"><span data-stu-id="98149-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="98149-119">3 000</span><span class="sxs-lookup"><span data-stu-id="98149-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98149-120">Максимальная частота входящих звонков для всех пользователей, для которых включена поддержка группового ответа на звонки, на пул в минуту</span><span class="sxs-lookup"><span data-stu-id="98149-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="98149-121">500</span><span class="sxs-lookup"><span data-stu-id="98149-121">500</span></span></p></td>
<td><p><span data-ttu-id="98149-122">60</span><span class="sxs-lookup"><span data-stu-id="98149-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98149-123">Максимальная частота восстановления звонков пользователями, для которых включена поддержка группового ответа на звонки, на пул в минуту</span><span class="sxs-lookup"><span data-stu-id="98149-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="98149-124">200</span><span class="sxs-lookup"><span data-stu-id="98149-124">200</span></span></p></td>
<td><p><span data-ttu-id="98149-125">24</span><span class="sxs-lookup"><span data-stu-id="98149-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="98149-126">Для пулов переднего плана, имеющих менее восьми серверов переднего плана, рассчитайте метрики линейно.</span><span class="sxs-lookup"><span data-stu-id="98149-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="98149-127">Например, если в пуле переднего плана есть один сервер переднего плана, вычислите максимальное значение Load в 1/8 для значений, указанных в таблице.</span><span class="sxs-lookup"><span data-stu-id="98149-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="98149-128">Вы можете увеличить или уменьшить рекомендованное число пользователей на группу и число групп при том условии, что не будет превышено максимальное число пользователей на пул.</span><span class="sxs-lookup"><span data-stu-id="98149-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="98149-129">Например, у вашего сервера Standard Edition может быть 120 групп с 25 пользователями на каждую группу, так как количество пользователей, включенных для отправки группового звонка, по-прежнему находится в пределах пользовательской модели (то 120 есть группового значения 25 пользователей — 3 000 пользователей для отправки групповых звонков).</span><span class="sxs-lookup"><span data-stu-id="98149-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

