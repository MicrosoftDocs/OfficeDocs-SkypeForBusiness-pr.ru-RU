---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 721932aa2929930b3da742355a46c5e2066c5c83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="a5acd-102">tblRoleType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5acd-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5acd-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="a5acd-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="a5acd-104">tblRoleType — это статическая таблица подстановки с типами ролей и сопоставленными с ними наборами разрешений.</span><span class="sxs-lookup"><span data-stu-id="a5acd-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="a5acd-105">Columns</span><span class="sxs-lookup"><span data-stu-id="a5acd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5acd-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="a5acd-106">Column</span></span></th>
<th><span data-ttu-id="a5acd-107">Тип</span><span class="sxs-lookup"><span data-stu-id="a5acd-107">Type</span></span></th>
<th><span data-ttu-id="a5acd-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a5acd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5acd-109">ртипеид</span><span class="sxs-lookup"><span data-stu-id="a5acd-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="a5acd-110">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="a5acd-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a5acd-111">Идентификатор типа роли.</span><span class="sxs-lookup"><span data-stu-id="a5acd-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5acd-112">ртипедеск</span><span class="sxs-lookup"><span data-stu-id="a5acd-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="a5acd-113">nvarchar (256), не NULL</span><span class="sxs-lookup"><span data-stu-id="a5acd-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a5acd-p101">Описание типа роли. Доступно четыре роли:</span><span class="sxs-lookup"><span data-stu-id="a5acd-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="a5acd-116">Member: член комнаты чата</span><span class="sxs-lookup"><span data-stu-id="a5acd-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="a5acd-117">Manager: руководитель комнаты чата</span><span class="sxs-lookup"><span data-stu-id="a5acd-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="a5acd-118">Voiced: выступающий для аудиторной комнаты чата</span><span class="sxs-lookup"><span data-stu-id="a5acd-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="a5acd-119">Creator: человек, который может создавать комнаты чата</span><span class="sxs-lookup"><span data-stu-id="a5acd-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5acd-120">ртипеалловедпермсет</span><span class="sxs-lookup"><span data-stu-id="a5acd-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="a5acd-121">bigint, не NULL</span><span class="sxs-lookup"><span data-stu-id="a5acd-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a5acd-p102">Набор разрешений для роли. Используются следующие биты:</span><span class="sxs-lookup"><span data-stu-id="a5acd-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a5acd-124">2: True if the role can manage nodes.</span><span class="sxs-lookup"><span data-stu-id="a5acd-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="a5acd-125">4: имеет значение true, если роль может создавать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="a5acd-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="a5acd-126">7: имеет значение true, если роль может присоединяться к комнате чата (или дочерним комнатам чата категории).</span><span class="sxs-lookup"><span data-stu-id="a5acd-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="a5acd-127">8: имеет значение true, если роль может общаться с помощью чата в комнате чата (или в дочерних комнатах чата категории).</span><span class="sxs-lookup"><span data-stu-id="a5acd-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="a5acd-128">10: имеет значение true, если роль может считывать журнал чата даже без присоединения к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="a5acd-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="a5acd-p103">11: имеет значение true, если роль может просматривать комнату чата. (Данная возможность дополнительно уточняется различными факторами, такими как область и видимость.)</span><span class="sxs-lookup"><span data-stu-id="a5acd-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="a5acd-131">12: имеет значение true, если роль может общаться с помощью чата в аудиторной комнате чата.</span><span class="sxs-lookup"><span data-stu-id="a5acd-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="a5acd-132">13: имеет значение true, если роль может обходить правила видимости при просмотре узлов.</span><span class="sxs-lookup"><span data-stu-id="a5acd-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a5acd-133">Key</span><span class="sxs-lookup"><span data-stu-id="a5acd-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5acd-134">Столбец</span><span class="sxs-lookup"><span data-stu-id="a5acd-134">Column</span></span></th>
<th><span data-ttu-id="a5acd-135">Описание</span><span class="sxs-lookup"><span data-stu-id="a5acd-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5acd-136">ртипеид</span><span class="sxs-lookup"><span data-stu-id="a5acd-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="a5acd-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a5acd-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

