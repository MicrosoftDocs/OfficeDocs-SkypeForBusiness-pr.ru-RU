---
title: 'Lync Server 2013: представление UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="bc19e-102">Представление "UserAgent" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc19e-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc19e-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="bc19e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="bc19e-104">В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="bc19e-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="bc19e-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc19e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc19e-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="bc19e-106">Column</span></span></th>
<th><span data-ttu-id="bc19e-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bc19e-107">Data Type</span></span></th>
<th><span data-ttu-id="bc19e-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="bc19e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc19e-109">Усераженткэй</span><span class="sxs-lookup"><span data-stu-id="bc19e-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="bc19e-110">целое</span><span class="sxs-lookup"><span data-stu-id="bc19e-110">int</span></span></p></td>
<td><p><span data-ttu-id="bc19e-111">Уникальный номер, идентифицирующий агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="bc19e-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc19e-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="bc19e-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="bc19e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bc19e-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bc19e-114">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="bc19e-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc19e-115">Уатипе</span><span class="sxs-lookup"><span data-stu-id="bc19e-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="bc19e-116">smallint</span><span class="sxs-lookup"><span data-stu-id="bc19e-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="bc19e-117">Тип агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="bc19e-117">Type of user agent.</span></span> <span data-ttu-id="bc19e-118">Дополнительные сведения приведены <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bc19e-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc19e-119">Уакатегори</span><span class="sxs-lookup"><span data-stu-id="bc19e-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="bc19e-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="bc19e-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="bc19e-121">Категория, к которой принадлежит агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="bc19e-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="bc19e-122">Например, агент пользователя КонференЦинг_аттендант_ 1.0 принадлежит к Уакатегори Каа.</span><span class="sxs-lookup"><span data-stu-id="bc19e-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

