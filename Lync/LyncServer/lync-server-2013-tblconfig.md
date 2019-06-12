---
title: 'Lync Server 2013: tblConfig'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745b8a1894ebca821474afdb82284fcf6bb09eb9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="c24fe-102">tblConfig в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24fe-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c24fe-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c24fe-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c24fe-104">Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.</span><span class="sxs-lookup"><span data-stu-id="c24fe-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="c24fe-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="c24fe-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c24fe-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="c24fe-106">Column</span></span></th>
<th><span data-ttu-id="c24fe-107">Тип</span><span class="sxs-lookup"><span data-stu-id="c24fe-107">Type</span></span></th>
<th><span data-ttu-id="c24fe-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c24fe-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c24fe-109">Конфиглабел</span><span class="sxs-lookup"><span data-stu-id="c24fe-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="c24fe-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c24fe-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="c24fe-111">&quot;Пул.&quot;</span><span class="sxs-lookup"><span data-stu-id="c24fe-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c24fe-112">Конфигконтент</span><span class="sxs-lookup"><span data-stu-id="c24fe-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="c24fe-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="c24fe-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="c24fe-114">Содержимое конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c24fe-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c24fe-115">Конфигпулид</span><span class="sxs-lookup"><span data-stu-id="c24fe-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="c24fe-116">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="c24fe-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c24fe-117">Уникальный идентификатор экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="c24fe-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c24fe-118">Ключ</span><span class="sxs-lookup"><span data-stu-id="c24fe-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c24fe-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="c24fe-119">Column</span></span></th>
<th><span data-ttu-id="c24fe-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c24fe-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c24fe-121">Конфиглабел</span><span class="sxs-lookup"><span data-stu-id="c24fe-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="c24fe-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c24fe-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

