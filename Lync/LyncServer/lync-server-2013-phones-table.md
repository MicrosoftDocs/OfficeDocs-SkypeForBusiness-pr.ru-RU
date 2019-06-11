---
title: 'Lync Server 2013: таблица Phones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920454a5db71c1e6f3cd2ea2ae1134d149b4f297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="5d3eb-102">Таблица Phones в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d3eb-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d3eb-103">_**Тема последнего изменения:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="5d3eb-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="5d3eb-104">Таблица phones является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="5d3eb-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="5d3eb-105">Каждая запись в таблице хранит информацию об одном номере телефона, который участвует в звонках по протоколу VoIP с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5d3eb-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d3eb-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="5d3eb-106">Column</span></span></th>
<th><span data-ttu-id="5d3eb-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5d3eb-107">Data Type</span></span></th>
<th><span data-ttu-id="5d3eb-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="5d3eb-108">Key/Index</span></span></th>
<th><span data-ttu-id="5d3eb-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="5d3eb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d3eb-110"><strong>Фонеид</strong></span><span class="sxs-lookup"><span data-stu-id="5d3eb-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3eb-111">целое</span><span class="sxs-lookup"><span data-stu-id="5d3eb-111">int</span></span></p></td>
<td><p><span data-ttu-id="5d3eb-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5d3eb-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5d3eb-113">Уникальный номер, идентифицирующий этот телефон.</span><span class="sxs-lookup"><span data-stu-id="5d3eb-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3eb-114"><strong>Фонеури</strong></span><span class="sxs-lookup"><span data-stu-id="5d3eb-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3eb-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d3eb-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d3eb-116">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="5d3eb-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3eb-117"><strong>Некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="5d3eb-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3eb-118">Датой</span><span class="sxs-lookup"><span data-stu-id="5d3eb-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3eb-119">Метка времени (только для внутреннего использования).</span><span class="sxs-lookup"><span data-stu-id="5d3eb-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="5d3eb-120">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d3eb-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

