---
title: 'Lync Server 2013: Тблпреференце'
description: 'Lync Server 2013: Тблпреференце.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547515"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="649e7-103">Тблпреференце в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="649e7-103">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="649e7-104">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="649e7-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="649e7-105">Тблпреференце содержит параметры клиента для пользователей.</span><span class="sxs-lookup"><span data-stu-id="649e7-105">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="649e7-106">Обычно они используются клиентами, предшествующими Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="649e7-106">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="649e7-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="649e7-107">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="649e7-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="649e7-108">Column</span></span></th>
<th><span data-ttu-id="649e7-109">Тип</span><span class="sxs-lookup"><span data-stu-id="649e7-109">Type</span></span></th>
<th><span data-ttu-id="649e7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="649e7-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="649e7-111">префлабел</span><span class="sxs-lookup"><span data-stu-id="649e7-111">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="649e7-112">nvarchar (255), не равно null</span><span class="sxs-lookup"><span data-stu-id="649e7-112">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="649e7-113">Метка с форматом: &lt; URI SIP пользователя &gt; | username. &lt; набор параметров &gt; .</span><span class="sxs-lookup"><span data-stu-id="649e7-113">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649e7-114">префсекид</span><span class="sxs-lookup"><span data-stu-id="649e7-114">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="649e7-115">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="649e7-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="649e7-116">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="649e7-116">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649e7-117">префконтент</span><span class="sxs-lookup"><span data-stu-id="649e7-117">prefContent</span></span></p></td>
<td><p><span data-ttu-id="649e7-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="649e7-118">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="649e7-119">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="649e7-119">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649e7-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="649e7-120">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="649e7-121">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="649e7-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="649e7-122">Идентификатор субъекта, обновившего параметр.</span><span class="sxs-lookup"><span data-stu-id="649e7-122">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="649e7-123">Key</span><span class="sxs-lookup"><span data-stu-id="649e7-123">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="649e7-124">Столбец</span><span class="sxs-lookup"><span data-stu-id="649e7-124">Column</span></span></th>
<th><span data-ttu-id="649e7-125">Описание</span><span class="sxs-lookup"><span data-stu-id="649e7-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="649e7-126">&lt;Префлабел, Префсекид&gt;</span><span class="sxs-lookup"><span data-stu-id="649e7-126">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="649e7-127">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="649e7-127">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

