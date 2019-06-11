---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="43884-102">tblSkippedAffiliations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43884-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43884-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="43884-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="43884-104">Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).</span><span class="sxs-lookup"><span data-stu-id="43884-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="43884-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="43884-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43884-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="43884-106">Column</span></span></th>
<th><span data-ttu-id="43884-107">Тип</span><span class="sxs-lookup"><span data-stu-id="43884-107">Type</span></span></th>
<th><span data-ttu-id="43884-108">Описание</span><span class="sxs-lookup"><span data-stu-id="43884-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43884-109">Принид</span><span class="sxs-lookup"><span data-stu-id="43884-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="43884-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="43884-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="43884-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="43884-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43884-112">Аффдескриптион</span><span class="sxs-lookup"><span data-stu-id="43884-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="43884-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="43884-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="43884-114">Строка, указывающая на принадлежность.</span><span class="sxs-lookup"><span data-stu-id="43884-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="43884-115">Формат: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="43884-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43884-116">Упдатедби</span><span class="sxs-lookup"><span data-stu-id="43884-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="43884-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="43884-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="43884-118">Идентификатор участника, который обновил эту строку.</span><span class="sxs-lookup"><span data-stu-id="43884-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="43884-119">Это всегда 1 (Системный пользователь), так как служба каталогов Active Directory — это единственный источник этих записей.</span><span class="sxs-lookup"><span data-stu-id="43884-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="43884-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="43884-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43884-121">Столбцы (-ы)</span><span class="sxs-lookup"><span data-stu-id="43884-121">Column(s)</span></span></th>
<th><span data-ttu-id="43884-122">Описание</span><span class="sxs-lookup"><span data-stu-id="43884-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43884-123">&lt;Принид, Аффдескриптион&gt;</span><span class="sxs-lookup"><span data-stu-id="43884-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="43884-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="43884-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43884-125">Принид</span><span class="sxs-lookup"><span data-stu-id="43884-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="43884-126">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="43884-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

