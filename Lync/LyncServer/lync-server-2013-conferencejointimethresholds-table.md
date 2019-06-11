---
title: 'Lync Server 2013: таблица Конференцежоинтимесрешолдс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="cc3e7-102">Таблица Конференцежоинтимесрешолдс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc3e7-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc3e7-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cc3e7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cc3e7-104">В таблице Конференцежоинтимесрешолдс содержатся ограничители классификации, используемые в сводном отчете "время присоединения к Конференции".</span><span class="sxs-lookup"><span data-stu-id="cc3e7-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="cc3e7-105">Сводный отчет о времени присоединения к Конференции суммирует количество времени, необходимого для успешного присоединения пользователей к Конференции; Эти значения времени выводятся как среднее значение и в одной из следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="cc3e7-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="cc3e7-106">Менее 2 секунд.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="cc3e7-107">От 2 секунды до 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="cc3e7-108">От 5 секунд до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="cc3e7-109">Более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-109">More than 10 seconds.</span></span>

<span data-ttu-id="cc3e7-110">В таблице Конференцежоинтимесрешолдс содержатся значения классификации 2 секунды, 5 секунд и 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="cc3e7-111">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc3e7-112">Столбец</span><span class="sxs-lookup"><span data-stu-id="cc3e7-112">Column</span></span></th>
<th><span data-ttu-id="cc3e7-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cc3e7-113">Data Type</span></span></th>
<th><span data-ttu-id="cc3e7-114">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="cc3e7-114">Key/Index</span></span></th>
<th><span data-ttu-id="cc3e7-115">Сведения</span><span class="sxs-lookup"><span data-stu-id="cc3e7-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc3e7-116"><strong>Срешолдид</strong></span><span class="sxs-lookup"><span data-stu-id="cc3e7-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="cc3e7-117">целое</span><span class="sxs-lookup"><span data-stu-id="cc3e7-117">int</span></span></p></td>
<td><p><span data-ttu-id="cc3e7-118">Primary</span><span class="sxs-lookup"><span data-stu-id="cc3e7-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="cc3e7-119">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc3e7-120"><strong>Срешолдвалуе</strong></span><span class="sxs-lookup"><span data-stu-id="cc3e7-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="cc3e7-121">целое</span><span class="sxs-lookup"><span data-stu-id="cc3e7-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc3e7-122">Верхний предел для классификации.</span><span class="sxs-lookup"><span data-stu-id="cc3e7-122">Upper limit for the classification.</span></span> <span data-ttu-id="cc3e7-123">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cc3e7-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="cc3e7-124">2</span><span class="sxs-lookup"><span data-stu-id="cc3e7-124">2</span></span></p></li>
<li><p><span data-ttu-id="cc3e7-125">5</span><span class="sxs-lookup"><span data-stu-id="cc3e7-125">5</span></span></p></li>
<li><p><span data-ttu-id="cc3e7-126">5-10</span><span class="sxs-lookup"><span data-stu-id="cc3e7-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

