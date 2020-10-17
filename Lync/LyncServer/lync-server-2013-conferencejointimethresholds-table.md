---
title: 'Lync Server 2013: таблица таблица conferencejointimethresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8dcf3d8b5f74abe6e145d7ac25e43411ca085c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502316"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="b9f3b-102">Таблица Таблица conferencejointimethresholds в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9f3b-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9f3b-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b9f3b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b9f3b-p101">Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="b9f3b-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="b9f3b-106">менее 2 секунд;</span><span class="sxs-lookup"><span data-stu-id="b9f3b-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="b9f3b-107">от 2 до 5 секунд;</span><span class="sxs-lookup"><span data-stu-id="b9f3b-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="b9f3b-108">от 5 до 10 секунд;</span><span class="sxs-lookup"><span data-stu-id="b9f3b-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="b9f3b-109">более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-109">More than 10 seconds.</span></span>

<span data-ttu-id="b9f3b-110">Таблица ConferenceJoinTimeThresholds содержит значения классификации для 2 секунд, 5 секунд и 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="b9f3b-111">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9f3b-112">Столбец</span><span class="sxs-lookup"><span data-stu-id="b9f3b-112">Column</span></span></th>
<th><span data-ttu-id="b9f3b-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b9f3b-113">Data Type</span></span></th>
<th><span data-ttu-id="b9f3b-114">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="b9f3b-114">Key/Index</span></span></th>
<th><span data-ttu-id="b9f3b-115">Сведения</span><span class="sxs-lookup"><span data-stu-id="b9f3b-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9f3b-116"><strong>срешолдид</strong></span><span class="sxs-lookup"><span data-stu-id="b9f3b-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9f3b-117">int</span><span class="sxs-lookup"><span data-stu-id="b9f3b-117">int</span></span></p></td>
<td><p><span data-ttu-id="b9f3b-118">Primary</span><span class="sxs-lookup"><span data-stu-id="b9f3b-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9f3b-119">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9f3b-120"><strong>срешолдвалуе</strong></span><span class="sxs-lookup"><span data-stu-id="b9f3b-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="b9f3b-121">int</span><span class="sxs-lookup"><span data-stu-id="b9f3b-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9f3b-p102">Верхняя граница для классификации. Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b9f3b-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="b9f3b-124">2</span><span class="sxs-lookup"><span data-stu-id="b9f3b-124">2</span></span></p></li>
<li><p><span data-ttu-id="b9f3b-125">5 </span><span class="sxs-lookup"><span data-stu-id="b9f3b-125">5</span></span></p></li>
<li><p><span data-ttu-id="b9f3b-126">10 </span><span class="sxs-lookup"><span data-stu-id="b9f3b-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

