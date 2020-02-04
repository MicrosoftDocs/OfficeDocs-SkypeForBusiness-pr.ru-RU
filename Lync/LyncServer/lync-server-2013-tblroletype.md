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
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="ca2cd-102">tblRoleType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca2cd-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca2cd-103">_**Тема последнего изменения:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ca2cd-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ca2cd-104">Тблролетипе — это статическая таблица подстановки с типами ролей и связанными с ними наборами разрешений.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="ca2cd-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="ca2cd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca2cd-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="ca2cd-106">Column</span></span></th>
<th><span data-ttu-id="ca2cd-107">Тип</span><span class="sxs-lookup"><span data-stu-id="ca2cd-107">Type</span></span></th>
<th><span data-ttu-id="ca2cd-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ca2cd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca2cd-109">ртипеид</span><span class="sxs-lookup"><span data-stu-id="ca2cd-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ca2cd-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ca2cd-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ca2cd-111">Идентификатор типа роли.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2cd-112">ртипедеск</span><span class="sxs-lookup"><span data-stu-id="ca2cd-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="ca2cd-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ca2cd-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ca2cd-114">Описание типа роли.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-114">Role type description.</span></span> <span data-ttu-id="ca2cd-115">Доступно четыре роли:</span><span class="sxs-lookup"><span data-stu-id="ca2cd-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="ca2cd-116">Член: участник комнаты чата</span><span class="sxs-lookup"><span data-stu-id="ca2cd-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-117">Руководитель: руководитель комнаты чата</span><span class="sxs-lookup"><span data-stu-id="ca2cd-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-118">Выставлено сообщение: выступающий для комнаты чата Аудиториум</span><span class="sxs-lookup"><span data-stu-id="ca2cd-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-119">Создатель: может создавать комнаты чата</span><span class="sxs-lookup"><span data-stu-id="ca2cd-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2cd-120">ртипеалловедпермсет</span><span class="sxs-lookup"><span data-stu-id="ca2cd-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="ca2cd-121">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ca2cd-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="ca2cd-122">Наборы разрешений для роли.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-122">Permission set for the role.</span></span> <span data-ttu-id="ca2cd-123">Используются следующие биты:</span><span class="sxs-lookup"><span data-stu-id="ca2cd-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ca2cd-124">2: значение true, если роль может управлять узлами.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-125">4: значение true, если роль может создавать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-126">7: значение true, если роль может присоединиться к комнате чата (или дочерним комнатам чатов для категории).</span><span class="sxs-lookup"><span data-stu-id="ca2cd-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-127">8: true, если роль может общаться в комнате чата (или в дочерних комнатах чата).</span><span class="sxs-lookup"><span data-stu-id="ca2cd-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-128">10: true, если роль может читать историю чата, даже если она не присоединяется к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-129">11: true, если роль может видеть комнату чата.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="ca2cd-130">(Это улучшено с помощью таких факторов, как область видимости и видимость.)</span><span class="sxs-lookup"><span data-stu-id="ca2cd-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-131">12: true, если роль может общаться в комнате чата Аудиториум.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="ca2cd-132">13: true, если роль может обойти правила видимости при просмотре узлов.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="ca2cd-133">Ключ</span><span class="sxs-lookup"><span data-stu-id="ca2cd-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca2cd-134">Столбец</span><span class="sxs-lookup"><span data-stu-id="ca2cd-134">Column</span></span></th>
<th><span data-ttu-id="ca2cd-135">Описание</span><span class="sxs-lookup"><span data-stu-id="ca2cd-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca2cd-136">ртипеид</span><span class="sxs-lookup"><span data-stu-id="ca2cd-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ca2cd-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="ca2cd-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

