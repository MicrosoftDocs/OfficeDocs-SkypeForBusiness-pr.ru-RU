---
title: 'Lync Server 2013: планирование мощности для группы ответа'
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
ms.openlocfilehash: d89e2882d3f1990a794e103849c1fa705caca98b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508116"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="8ce72-102">Планирование емкости для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ce72-102">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ce72-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8ce72-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="8ce72-104">В следующей таблице описывается пользовательская модель группы ответа, которую можно использовать в качестве основы для требований по планированию мощности.</span><span class="sxs-lookup"><span data-stu-id="8ce72-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ce72-p101">Значения приведены для звуковых файлов группы ответа со следующими характеристиками: 16-разрядный файл с расширением WAV и частотой 16 кГц в монофонической записи. Если вы используете другие форматы файлов, например Windows Media Audio (WMA), характеристики могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="8ce72-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8ce72-107">При планировании мощности аварийного восстановления для парных пулов необходимо учитывать, что каждый пул, входящий в состав парного пула, должен обрабатывать рабочие нагрузки всех групп ответа в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="8ce72-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="8ce72-108">Пользовательская модель группы ответа</span><span class="sxs-lookup"><span data-stu-id="8ce72-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ce72-109">Метрика</span><span class="sxs-lookup"><span data-stu-id="8ce72-109">Metric</span></span></th>
<th><span data-ttu-id="8ce72-110">Для пула корпоративных выпусков (с 8 серверами переднего плана)</span><span class="sxs-lookup"><span data-stu-id="8ce72-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="8ce72-111">Для каждого сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8ce72-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ce72-112">Входящих звонков в секунду</span><span class="sxs-lookup"><span data-stu-id="8ce72-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="8ce72-113">16 </span><span class="sxs-lookup"><span data-stu-id="8ce72-113">16</span></span></p></td>
<td><p><span data-ttu-id="8ce72-114">2</span><span class="sxs-lookup"><span data-stu-id="8ce72-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ce72-115">Число звонков, одновременно подключенных к интерактивному автоответчику или находящихся на удержании</span><span class="sxs-lookup"><span data-stu-id="8ce72-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="8ce72-116">480</span><span class="sxs-lookup"><span data-stu-id="8ce72-116">480</span></span></p></td>
<td><p><span data-ttu-id="8ce72-117">60</span><span class="sxs-lookup"><span data-stu-id="8ce72-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ce72-118">Число одновременных анонимных сеансов (без учета сеансов обмена мгновенными сообщениями)</span><span class="sxs-lookup"><span data-stu-id="8ce72-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="8ce72-119">224</span><span class="sxs-lookup"><span data-stu-id="8ce72-119">224</span></span></p></td>
<td><p><span data-ttu-id="8ce72-120">8</span><span class="sxs-lookup"><span data-stu-id="8ce72-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ce72-121">Число одновременных анонимных сеансов (с учетом сеансов обмена мгновенными сообщениями)</span><span class="sxs-lookup"><span data-stu-id="8ce72-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="8ce72-122">64</span><span class="sxs-lookup"><span data-stu-id="8ce72-122">64</span></span></p></td>
<td><p><span data-ttu-id="8ce72-123">8 </span><span class="sxs-lookup"><span data-stu-id="8ce72-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ce72-124">Число активных агентов (официальные и неофициальные)</span><span class="sxs-lookup"><span data-stu-id="8ce72-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="8ce72-125">1200</span><span class="sxs-lookup"><span data-stu-id="8ce72-125">1200</span></span></p></td>
<td><p><span data-ttu-id="8ce72-126">1200</span><span class="sxs-lookup"><span data-stu-id="8ce72-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ce72-127">Число сервисных групп</span><span class="sxs-lookup"><span data-stu-id="8ce72-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="8ce72-128">400</span><span class="sxs-lookup"><span data-stu-id="8ce72-128">400</span></span></p></td>
<td><p><span data-ttu-id="8ce72-129">400</span><span class="sxs-lookup"><span data-stu-id="8ce72-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ce72-130">Число групп интерактивного автоответчика (распознавание речи)</span><span class="sxs-lookup"><span data-stu-id="8ce72-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="8ce72-131">200</span><span class="sxs-lookup"><span data-stu-id="8ce72-131">200</span></span></p></td>
<td><p><span data-ttu-id="8ce72-132">200</span><span class="sxs-lookup"><span data-stu-id="8ce72-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

