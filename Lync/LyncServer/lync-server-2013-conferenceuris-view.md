---
title: 'Lync Server 2013: представление Таблица conferenceuris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris view
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49733750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77fc7e9cac8b253dd6e86923938b5d92b916bcda
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferenceuris-view-in-lync-server-2013"></a><span data-ttu-id="ad1b8-102">Представление Таблица conferenceuris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad1b8-102">ConferenceUris view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad1b8-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ad1b8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ad1b8-104">В представлении ConfernceUris хранятся сведения об идентификаторах URI, которые участвовали в сеансах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ad1b8-104">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="ad1b8-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad1b8-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad1b8-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="ad1b8-106">Column</span></span></th>
<th><span data-ttu-id="ad1b8-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ad1b8-107">Data Type</span></span></th>
<th><span data-ttu-id="ad1b8-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="ad1b8-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad1b8-109">конференцеуриид</span><span class="sxs-lookup"><span data-stu-id="ad1b8-109">ConferenceUriId</span></span></p></td>
<td><p><span data-ttu-id="ad1b8-110">int</span><span class="sxs-lookup"><span data-stu-id="ad1b8-110">int</span></span></p></td>
<td><p><span data-ttu-id="ad1b8-111">Уникальный номер, идентифицирующий URI конференции.</span><span class="sxs-lookup"><span data-stu-id="ad1b8-111">Unique number identifying the conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad1b8-112">конференцеури</span><span class="sxs-lookup"><span data-stu-id="ad1b8-112">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="ad1b8-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ad1b8-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ad1b8-114">Идентификатор URI конференции.</span><span class="sxs-lookup"><span data-stu-id="ad1b8-114">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad1b8-115">конференцеуритипе</span><span class="sxs-lookup"><span data-stu-id="ad1b8-115">ConferenceUriType</span></span></p></td>
<td><p><span data-ttu-id="ad1b8-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ad1b8-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad1b8-117">Тип идентификатора URI конференции.</span><span class="sxs-lookup"><span data-stu-id="ad1b8-117">Type of conference URI.</span></span> <span data-ttu-id="ad1b8-118">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad1b8-118">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

