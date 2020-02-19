---
title: 'Lync Server 2013: таблица таблица deregistertype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f1bee5dfa5a0f24b46ba51abafee8d0a89b0a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="92118-102">Таблица Таблица deregistertype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92118-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92118-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="92118-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="92118-104">Таблица DeRegisterType — это статическая таблица, в которой хранится список возможных типов отмены регистрации пользователей, например «Инициируется клиентом», «Срок действия регистрации истек», «Клиент перестал отвечать».</span><span class="sxs-lookup"><span data-stu-id="92118-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92118-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="92118-105">Column</span></span></th>
<th><span data-ttu-id="92118-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="92118-106">Data Type</span></span></th>
<th><span data-ttu-id="92118-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="92118-107">Key/Index</span></span></th>
<th><span data-ttu-id="92118-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="92118-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92118-109"><strong>дерегистертипеид</strong></span><span class="sxs-lookup"><span data-stu-id="92118-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="92118-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="92118-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="92118-111">Primary</span><span class="sxs-lookup"><span data-stu-id="92118-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92118-112"><strong>дерегистерреасон</strong></span><span class="sxs-lookup"><span data-stu-id="92118-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="92118-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="92118-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92118-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="92118-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="92118-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="92118-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="92118-116">1 — клиент инициировал отмену регистрации</span><span class="sxs-lookup"><span data-stu-id="92118-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="92118-117">2 — срок действия регистрации истек</span><span class="sxs-lookup"><span data-stu-id="92118-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="92118-118">3 — аварийное завершение клиента</span><span class="sxs-lookup"><span data-stu-id="92118-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="92118-119">4 — атрибуты пользователя изменены</span><span class="sxs-lookup"><span data-stu-id="92118-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="92118-120">5 — предпочтительный регистратор изменен</span><span class="sxs-lookup"><span data-stu-id="92118-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="92118-121">6 — устаревший клиент в режиме сохранения</span><span class="sxs-lookup"><span data-stu-id="92118-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

