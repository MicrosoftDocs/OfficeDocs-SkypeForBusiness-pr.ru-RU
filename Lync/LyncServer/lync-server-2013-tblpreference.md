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
ms.openlocfilehash: a9d91a11f6813bfc7ef86eaf5efded41c7af0c63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="a7a51-102">Тблпреференце в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7a51-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7a51-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="a7a51-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="a7a51-104">Тблпреференце содержит параметры клиента для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a7a51-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="a7a51-105">Обычно они используются клиентами, предшествующими Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a7a51-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="a7a51-106">Columns</span><span class="sxs-lookup"><span data-stu-id="a7a51-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7a51-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="a7a51-107">Column</span></span></th>
<th><span data-ttu-id="a7a51-108">Тип</span><span class="sxs-lookup"><span data-stu-id="a7a51-108">Type</span></span></th>
<th><span data-ttu-id="a7a51-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a7a51-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7a51-110">префлабел</span><span class="sxs-lookup"><span data-stu-id="a7a51-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="a7a51-111">nvarchar (255), не равно null</span><span class="sxs-lookup"><span data-stu-id="a7a51-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="a7a51-112">Метка с форматом: &lt;URI&gt;SIP пользователя | username. &lt;набор&gt;параметров.</span><span class="sxs-lookup"><span data-stu-id="a7a51-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7a51-113">префсекид</span><span class="sxs-lookup"><span data-stu-id="a7a51-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="a7a51-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="a7a51-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a7a51-115">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="a7a51-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7a51-116">префконтент</span><span class="sxs-lookup"><span data-stu-id="a7a51-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="a7a51-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a7a51-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="a7a51-118">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="a7a51-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7a51-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="a7a51-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="a7a51-120">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="a7a51-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a7a51-121">Идентификатор субъекта, обновившего параметр.</span><span class="sxs-lookup"><span data-stu-id="a7a51-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a7a51-122">Key</span><span class="sxs-lookup"><span data-stu-id="a7a51-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7a51-123">Столбец</span><span class="sxs-lookup"><span data-stu-id="a7a51-123">Column</span></span></th>
<th><span data-ttu-id="a7a51-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a7a51-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7a51-125">&lt;Префлабел, Префсекид&gt;</span><span class="sxs-lookup"><span data-stu-id="a7a51-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a7a51-126">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a7a51-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

