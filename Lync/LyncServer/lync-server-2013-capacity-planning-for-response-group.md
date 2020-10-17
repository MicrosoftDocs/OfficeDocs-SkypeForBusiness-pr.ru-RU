---
title: 'Lync Server 2013: планирование мощности для группы ответа'
description: 'Lync Server 2013: планирование мощности для группы ответа.'
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
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544435"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="8f215-103">Планирование емкости для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f215-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f215-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8f215-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="8f215-105">В следующей таблице описывается пользовательская модель группы ответа, которую можно использовать в качестве основы для требований по планированию мощности.</span><span class="sxs-lookup"><span data-stu-id="8f215-105">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f215-p101">Значения приведены для звуковых файлов группы ответа со следующими характеристиками: 16-разрядный файл с расширением WAV и частотой 16 кГц в монофонической записи. Если вы используете другие форматы файлов, например Windows Media Audio (WMA), характеристики могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="8f215-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8f215-108">При планировании мощности аварийного восстановления для парных пулов необходимо учитывать, что каждый пул, входящий в состав парного пула, должен обрабатывать рабочие нагрузки всех групп ответа в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="8f215-108">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="8f215-109">Пользовательская модель группы ответа</span><span class="sxs-lookup"><span data-stu-id="8f215-109">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f215-110">Метрика</span><span class="sxs-lookup"><span data-stu-id="8f215-110">Metric</span></span></th>
<th><span data-ttu-id="8f215-111">Для пула корпоративных выпусков (с 8 серверами переднего плана)</span><span class="sxs-lookup"><span data-stu-id="8f215-111">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="8f215-112">Для каждого сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8f215-112">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f215-113">Входящих звонков в секунду</span><span class="sxs-lookup"><span data-stu-id="8f215-113">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="8f215-114">16 </span><span class="sxs-lookup"><span data-stu-id="8f215-114">16</span></span></p></td>
<td><p><span data-ttu-id="8f215-115">2</span><span class="sxs-lookup"><span data-stu-id="8f215-115">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f215-116">Число звонков, одновременно подключенных к интерактивному автоответчику или находящихся на удержании</span><span class="sxs-lookup"><span data-stu-id="8f215-116">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="8f215-117">480</span><span class="sxs-lookup"><span data-stu-id="8f215-117">480</span></span></p></td>
<td><p><span data-ttu-id="8f215-118">60</span><span class="sxs-lookup"><span data-stu-id="8f215-118">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f215-119">Число одновременных анонимных сеансов (без учета сеансов обмена мгновенными сообщениями)</span><span class="sxs-lookup"><span data-stu-id="8f215-119">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="8f215-120">224</span><span class="sxs-lookup"><span data-stu-id="8f215-120">224</span></span></p></td>
<td><p><span data-ttu-id="8f215-121">8</span><span class="sxs-lookup"><span data-stu-id="8f215-121">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f215-122">Число одновременных анонимных сеансов (с учетом сеансов обмена мгновенными сообщениями)</span><span class="sxs-lookup"><span data-stu-id="8f215-122">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="8f215-123">64</span><span class="sxs-lookup"><span data-stu-id="8f215-123">64</span></span></p></td>
<td><p><span data-ttu-id="8f215-124">8 </span><span class="sxs-lookup"><span data-stu-id="8f215-124">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f215-125">Число активных агентов (официальные и неофициальные)</span><span class="sxs-lookup"><span data-stu-id="8f215-125">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="8f215-126">1200</span><span class="sxs-lookup"><span data-stu-id="8f215-126">1200</span></span></p></td>
<td><p><span data-ttu-id="8f215-127">1200</span><span class="sxs-lookup"><span data-stu-id="8f215-127">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f215-128">Число сервисных групп</span><span class="sxs-lookup"><span data-stu-id="8f215-128">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="8f215-129">400</span><span class="sxs-lookup"><span data-stu-id="8f215-129">400</span></span></p></td>
<td><p><span data-ttu-id="8f215-130">400</span><span class="sxs-lookup"><span data-stu-id="8f215-130">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f215-131">Число групп интерактивного автоответчика (распознавание речи)</span><span class="sxs-lookup"><span data-stu-id="8f215-131">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="8f215-132">200</span><span class="sxs-lookup"><span data-stu-id="8f215-132">200</span></span></p></td>
<td><p><span data-ttu-id="8f215-133">200</span><span class="sxs-lookup"><span data-stu-id="8f215-133">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

