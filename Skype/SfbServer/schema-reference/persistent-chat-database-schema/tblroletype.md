---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType — это статическая таблица подстановки с типами ролей и их наборы разрешений.
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883147"
---
# <a name="tblroletype"></a><span data-ttu-id="3d9b1-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="3d9b1-103">tblRoleType</span></span>
 
<span data-ttu-id="3d9b1-104">tblRoleType — это статическая таблица подстановки с типами ролей и их наборы разрешений.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="3d9b1-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="3d9b1-105">**Columns**</span></span>

|<span data-ttu-id="3d9b1-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3d9b1-106">**Column**</span></span>|<span data-ttu-id="3d9b1-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3d9b1-107">**Type**</span></span>|<span data-ttu-id="3d9b1-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d9b1-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="3d9b1-109">rtypeID</span></span>  <br/> |<span data-ttu-id="3d9b1-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="3d9b1-110">int, not null</span></span>  <br/> |<span data-ttu-id="3d9b1-111">Идентификатор типа роли.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="3d9b1-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="3d9b1-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="3d9b1-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="3d9b1-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="3d9b1-114">Описание типа роли.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-114">Role type description.</span></span> <span data-ttu-id="3d9b1-115">Существует четыре доступных ролей:</span><span class="sxs-lookup"><span data-stu-id="3d9b1-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="3d9b1-116">Member: член комнаты чата</span><span class="sxs-lookup"><span data-stu-id="3d9b1-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="3d9b1-117">Manager: руководитель комнаты чата</span><span class="sxs-lookup"><span data-stu-id="3d9b1-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="3d9b1-118">Voiced: Выступающий для аудиторной комнаты чата</span><span class="sxs-lookup"><span data-stu-id="3d9b1-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="3d9b1-119">Creator: Может создавать комнаты чата</span><span class="sxs-lookup"><span data-stu-id="3d9b1-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="3d9b1-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="3d9b1-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="3d9b1-121">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="3d9b1-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="3d9b1-122">Набор разрешений для роли.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-122">Permission set for the role.</span></span> <span data-ttu-id="3d9b1-123">Используемые биты:</span><span class="sxs-lookup"><span data-stu-id="3d9b1-123">The used bits are:</span></span> <br/>  <span data-ttu-id="3d9b1-124">2: имеет значение true, если роль может управлять узлов.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="3d9b1-125">4: имеет значение true, если роль может создавать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="3d9b1-126">7: имеет значение true, если роль может присоединяться к комнате чата (или дочерним комнатам чата категории).</span><span class="sxs-lookup"><span data-stu-id="3d9b1-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="3d9b1-127">8: имеет значение true, если роль может общаться в комнате чата (или в дочерних комнатах чата категории).</span><span class="sxs-lookup"><span data-stu-id="3d9b1-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="3d9b1-128">10: имеет значение true, если роль может считывать журнал чата даже в том случае, если не подключен к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="3d9b1-129">11: имеет значение true, если роль может просматривать комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="3d9b1-130">(Это является дальнейшей уточнение по факторов, например, области и видимости.)</span><span class="sxs-lookup"><span data-stu-id="3d9b1-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="3d9b1-131">12: имеет значение true, если роль может общаться в чате аудитории.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="3d9b1-132">13: имеет значение true, если роль может обходить правила видимости при просмотре узлов.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="3d9b1-133">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="3d9b1-133">**Key**</span></span>

|<span data-ttu-id="3d9b1-134">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3d9b1-134">**Column**</span></span>|<span data-ttu-id="3d9b1-135">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3d9b1-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="3d9b1-136">rtypeID</span></span>  <br/> |<span data-ttu-id="3d9b1-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="3d9b1-137">Primary key.</span></span>  <br/> |
   

