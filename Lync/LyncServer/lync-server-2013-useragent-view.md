---
title: 'Lync Server 2013: представление UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25ea12241c841edf4ac758e62ad89c96de88a7cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="f9aff-102">Представление UserAgent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9aff-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9aff-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f9aff-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f9aff-104">В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи.</span><span class="sxs-lookup"><span data-stu-id="f9aff-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="f9aff-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9aff-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9aff-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="f9aff-106">Column</span></span></th>
<th><span data-ttu-id="f9aff-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f9aff-107">Data Type</span></span></th>
<th><span data-ttu-id="f9aff-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="f9aff-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9aff-109">усераженткэй</span><span class="sxs-lookup"><span data-stu-id="f9aff-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="f9aff-110">int</span><span class="sxs-lookup"><span data-stu-id="f9aff-110">int</span></span></p></td>
<td><p><span data-ttu-id="f9aff-111">Уникальное число, идентифицирующее этот агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9aff-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9aff-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="f9aff-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="f9aff-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f9aff-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9aff-114">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9aff-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9aff-115">UAType</span><span class="sxs-lookup"><span data-stu-id="f9aff-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="f9aff-116">smallint</span><span class="sxs-lookup"><span data-stu-id="f9aff-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="f9aff-117">Тип агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9aff-117">Type of user agent.</span></span> <span data-ttu-id="f9aff-118">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f9aff-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9aff-119">уакатегори</span><span class="sxs-lookup"><span data-stu-id="f9aff-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="f9aff-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f9aff-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f9aff-p103">Категория, к которой принадлежит агент пользователя. Например, агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="f9aff-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

