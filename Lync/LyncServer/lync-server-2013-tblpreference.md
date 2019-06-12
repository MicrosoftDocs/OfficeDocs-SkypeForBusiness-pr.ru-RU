---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 652312c5ca48a140ee7f17486ef98debb4e08672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="0e95f-102">tblPreference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e95f-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e95f-103">_**Тема последнего изменения:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="0e95f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="0e95f-104">Тблпреференце включает клиентские настройки пользователей.</span><span class="sxs-lookup"><span data-stu-id="0e95f-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="0e95f-105">Обычно используется клиентами, предшествующими Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0e95f-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="0e95f-106">Столбцов</span><span class="sxs-lookup"><span data-stu-id="0e95f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e95f-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="0e95f-107">Column</span></span></th>
<th><span data-ttu-id="0e95f-108">Тип</span><span class="sxs-lookup"><span data-stu-id="0e95f-108">Type</span></span></th>
<th><span data-ttu-id="0e95f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0e95f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e95f-110">Префлабел</span><span class="sxs-lookup"><span data-stu-id="0e95f-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="0e95f-111">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0e95f-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="0e95f-112">Надпись с таким же форматом &lt;, как:&gt;URI SIP пользователя, | имя пользователя. &lt;наборы&gt;параметров.</span><span class="sxs-lookup"><span data-stu-id="0e95f-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e95f-113">Префсекид</span><span class="sxs-lookup"><span data-stu-id="0e95f-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="0e95f-114">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0e95f-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0e95f-115">Последовательный номер (на метку) для целей управления версиями.</span><span class="sxs-lookup"><span data-stu-id="0e95f-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e95f-116">Префконтент</span><span class="sxs-lookup"><span data-stu-id="0e95f-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="0e95f-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="0e95f-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="0e95f-118">Закодированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="0e95f-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e95f-119">Ластмодифиедби</span><span class="sxs-lookup"><span data-stu-id="0e95f-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="0e95f-120">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0e95f-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0e95f-121">Идентификатор участника, который обновил предпочтение.</span><span class="sxs-lookup"><span data-stu-id="0e95f-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0e95f-122">Ключ</span><span class="sxs-lookup"><span data-stu-id="0e95f-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e95f-123">Столбец</span><span class="sxs-lookup"><span data-stu-id="0e95f-123">Column</span></span></th>
<th><span data-ttu-id="0e95f-124">Описание</span><span class="sxs-lookup"><span data-stu-id="0e95f-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e95f-125">&lt;Префлабел, Префсекид&gt;</span><span class="sxs-lookup"><span data-stu-id="0e95f-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="0e95f-126">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="0e95f-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

