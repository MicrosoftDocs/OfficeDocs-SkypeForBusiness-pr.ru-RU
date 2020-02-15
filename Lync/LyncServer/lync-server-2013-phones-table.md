---
title: 'Lync Server 2013: таблица phones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c3a67381a101bd9aecc4872d4e08b4fb8daea3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="7bb57-102">Таблица phones в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bb57-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bb57-103">_**Последнее изменение темы:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="7bb57-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="7bb57-104">Таблица phones это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="7bb57-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="7bb57-105">Каждая запись в таблице содержит сведения об одном номере телефона, участвующем в вызовах VoIP с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7bb57-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bb57-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="7bb57-106">Column</span></span></th>
<th><span data-ttu-id="7bb57-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7bb57-107">Data Type</span></span></th>
<th><span data-ttu-id="7bb57-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="7bb57-108">Key/Index</span></span></th>
<th><span data-ttu-id="7bb57-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7bb57-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bb57-110"><strong>фонеид</strong></span><span class="sxs-lookup"><span data-stu-id="7bb57-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="7bb57-111">int</span><span class="sxs-lookup"><span data-stu-id="7bb57-111">int</span></span></p></td>
<td><p><span data-ttu-id="7bb57-112">Primary</span><span class="sxs-lookup"><span data-stu-id="7bb57-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7bb57-113">Уникальный номер, идентифицирующий этот телефон.</span><span class="sxs-lookup"><span data-stu-id="7bb57-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bb57-114"><strong>фонеури</strong></span><span class="sxs-lookup"><span data-stu-id="7bb57-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7bb57-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7bb57-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7bb57-116">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="7bb57-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bb57-117"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="7bb57-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="7bb57-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="7bb57-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7bb57-119">Отметка времени (только для внутреннего использования).</span><span class="sxs-lookup"><span data-stu-id="7bb57-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="7bb57-120">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7bb57-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

