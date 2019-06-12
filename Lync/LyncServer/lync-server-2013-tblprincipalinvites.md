---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="f3c32-102">tblPrincipalInvites в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c32-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3c32-103">_**Тема последнего изменения:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f3c32-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f3c32-104">ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.</span><span class="sxs-lookup"><span data-stu-id="f3c32-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="f3c32-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="f3c32-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3c32-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="f3c32-106">Column</span></span></th>
<th><span data-ttu-id="f3c32-107">Тип</span><span class="sxs-lookup"><span data-stu-id="f3c32-107">Type</span></span></th>
<th><span data-ttu-id="f3c32-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f3c32-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3c32-109">Принид</span><span class="sxs-lookup"><span data-stu-id="f3c32-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="f3c32-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f3c32-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f3c32-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="f3c32-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c32-112">ИНВИД</span><span class="sxs-lookup"><span data-stu-id="f3c32-112">invID</span></span></p></td>
<td><p><span data-ttu-id="f3c32-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f3c32-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f3c32-114">Уникальный последовательный номер (для идентификатора участника), сформированный из таблицы Тблластинвитеид.</span><span class="sxs-lookup"><span data-stu-id="f3c32-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c32-115">Нодеид</span><span class="sxs-lookup"><span data-stu-id="f3c32-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f3c32-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f3c32-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f3c32-117">Идентификатор узла (только для комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="f3c32-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c32-118">Креатедон</span><span class="sxs-lookup"><span data-stu-id="f3c32-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="f3c32-119">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f3c32-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f3c32-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="f3c32-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f3c32-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3c32-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3c32-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="f3c32-122">Column</span></span></th>
<th><span data-ttu-id="f3c32-123">Описание</span><span class="sxs-lookup"><span data-stu-id="f3c32-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3c32-124">&lt;Принид, Нодеид&gt;</span><span class="sxs-lookup"><span data-stu-id="f3c32-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f3c32-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f3c32-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c32-126">Принид</span><span class="sxs-lookup"><span data-stu-id="f3c32-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="f3c32-127">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="f3c32-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c32-128">Нодеид</span><span class="sxs-lookup"><span data-stu-id="f3c32-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f3c32-129">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="f3c32-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

