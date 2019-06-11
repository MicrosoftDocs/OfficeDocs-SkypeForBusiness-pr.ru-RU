---
title: 'Lync Server 2013: таблица DeRegisterType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97d25ded1a281df0774644cd0d69f5e12d9c85a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="7f49b-102">Таблица DeRegisterType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f49b-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f49b-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7f49b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7f49b-104">Таблица Дерегистертипе — это статическая таблица, в которой хранится список возможных типов отмены регистров пользователей, например "инициировано клиентом", "регистрация просрочено" или "клиент перестает отвечать на запросы".</span><span class="sxs-lookup"><span data-stu-id="7f49b-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f49b-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="7f49b-105">Column</span></span></th>
<th><span data-ttu-id="7f49b-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7f49b-106">Data Type</span></span></th>
<th><span data-ttu-id="7f49b-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="7f49b-107">Key/Index</span></span></th>
<th><span data-ttu-id="7f49b-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="7f49b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f49b-109"><strong>Дерегистертипеид</strong></span><span class="sxs-lookup"><span data-stu-id="7f49b-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="7f49b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7f49b-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7f49b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7f49b-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f49b-112"><strong>Дерегистерреасон</strong></span><span class="sxs-lookup"><span data-stu-id="7f49b-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="7f49b-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7f49b-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f49b-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="7f49b-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="7f49b-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="7f49b-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="7f49b-116">1 — клиент инициировал отмену регистрации</span><span class="sxs-lookup"><span data-stu-id="7f49b-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="7f49b-117">2 — срок действия регистрации истек</span><span class="sxs-lookup"><span data-stu-id="7f49b-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="7f49b-118">3 – сбой клиента</span><span class="sxs-lookup"><span data-stu-id="7f49b-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="7f49b-119">4 — изменились атрибуты пользователя</span><span class="sxs-lookup"><span data-stu-id="7f49b-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="7f49b-120">5 — основной регистратор изменился</span><span class="sxs-lookup"><span data-stu-id="7f49b-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="7f49b-121">6 — устаревший клиент в режиме выживания</span><span class="sxs-lookup"><span data-stu-id="7f49b-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

