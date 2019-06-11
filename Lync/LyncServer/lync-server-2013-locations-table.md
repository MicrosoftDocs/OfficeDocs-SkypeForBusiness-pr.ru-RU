---
title: 'Lync Server 2013: таблица Locations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b26f8c30c0d26fd265d95542b79f919153bc15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="9c86a-102">Таблица Locations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c86a-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c86a-103">_**Тема последнего изменения:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="9c86a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="9c86a-104">Каждая запись представляет одну ссылку на расположение в экстренном звонке, например, в вызове E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9c86a-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c86a-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="9c86a-105">Column</span></span></th>
<th><span data-ttu-id="9c86a-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9c86a-106">Data Type</span></span></th>
<th><span data-ttu-id="9c86a-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="9c86a-107">Key/Index</span></span></th>
<th><span data-ttu-id="9c86a-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="9c86a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c86a-109"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="9c86a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c86a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9c86a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c86a-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="9c86a-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9c86a-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="9c86a-112">Time of session request.</span></span> <span data-ttu-id="9c86a-113">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="9c86a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9c86a-114">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9c86a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c86a-115"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="9c86a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9c86a-116">целое</span><span class="sxs-lookup"><span data-stu-id="9c86a-116">int</span></span></p></td>
<td><p><span data-ttu-id="9c86a-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="9c86a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9c86a-118">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="9c86a-118">ID number to identify the session.</span></span> <span data-ttu-id="9c86a-119">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="9c86a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9c86a-120">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9c86a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c86a-121"><strong>Расположение</strong></span><span class="sxs-lookup"><span data-stu-id="9c86a-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="9c86a-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="9c86a-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9c86a-123">Место вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="9c86a-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

