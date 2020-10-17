---
title: 'Lync Server 2013: Тблпреференце'
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
ms.openlocfilehash: ef0ee11cd780037410ea1d7e0d94c83e139d8418
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523776"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="69088-102">Тблпреференце в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69088-102">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69088-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="69088-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="69088-104">Тблпреференце содержит параметры клиента для пользователей.</span><span class="sxs-lookup"><span data-stu-id="69088-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="69088-105">Обычно они используются клиентами, предшествующими Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="69088-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="69088-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="69088-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69088-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="69088-107">Column</span></span></th>
<th><span data-ttu-id="69088-108">Тип</span><span class="sxs-lookup"><span data-stu-id="69088-108">Type</span></span></th>
<th><span data-ttu-id="69088-109">Описание</span><span class="sxs-lookup"><span data-stu-id="69088-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69088-110">префлабел</span><span class="sxs-lookup"><span data-stu-id="69088-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="69088-111">nvarchar (255), не равно null</span><span class="sxs-lookup"><span data-stu-id="69088-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="69088-112">Метка с форматом: &lt; URI SIP пользователя &gt; | username. &lt; набор параметров &gt; .</span><span class="sxs-lookup"><span data-stu-id="69088-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69088-113">префсекид</span><span class="sxs-lookup"><span data-stu-id="69088-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="69088-114">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="69088-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69088-115">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="69088-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69088-116">префконтент</span><span class="sxs-lookup"><span data-stu-id="69088-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="69088-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="69088-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="69088-118">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="69088-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69088-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="69088-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="69088-120">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="69088-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69088-121">Идентификатор субъекта, обновившего параметр.</span><span class="sxs-lookup"><span data-stu-id="69088-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="69088-122">Key</span><span class="sxs-lookup"><span data-stu-id="69088-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69088-123">Столбец</span><span class="sxs-lookup"><span data-stu-id="69088-123">Column</span></span></th>
<th><span data-ttu-id="69088-124">Описание</span><span class="sxs-lookup"><span data-stu-id="69088-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69088-125">&lt;Префлабел, Префсекид&gt;</span><span class="sxs-lookup"><span data-stu-id="69088-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="69088-126">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="69088-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

