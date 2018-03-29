---
title: tblRoleType
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
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a><span data-ttu-id="682aa-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="682aa-103">tblRoleType</span></span>
 
<span data-ttu-id="682aa-104">tblRoleType — это статическая таблица подстановки с типами ролей и их наборы разрешений.</span><span class="sxs-lookup"><span data-stu-id="682aa-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="682aa-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="682aa-105">**Columns**</span></span>

|<span data-ttu-id="682aa-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="682aa-106">**Column**</span></span>|<span data-ttu-id="682aa-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="682aa-107">**Type**</span></span>|<span data-ttu-id="682aa-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="682aa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="682aa-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="682aa-109">rtypeID</span></span>  <br/> |<span data-ttu-id="682aa-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="682aa-110">int, not null</span></span>  <br/> |<span data-ttu-id="682aa-111">Идентификатор типа роли.</span><span class="sxs-lookup"><span data-stu-id="682aa-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="682aa-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="682aa-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="682aa-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="682aa-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="682aa-114">Описание типа роли.</span><span class="sxs-lookup"><span data-stu-id="682aa-114">Role type description.</span></span> <span data-ttu-id="682aa-115">Существует четыре доступных ролей:</span><span class="sxs-lookup"><span data-stu-id="682aa-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="682aa-116">Member: член комнаты чата</span><span class="sxs-lookup"><span data-stu-id="682aa-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="682aa-117">Manager: руководитель комнаты чата</span><span class="sxs-lookup"><span data-stu-id="682aa-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="682aa-118">Voiced: Выступающий для аудиторной комнаты чата</span><span class="sxs-lookup"><span data-stu-id="682aa-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="682aa-119">Creator: Может создавать комнаты чата</span><span class="sxs-lookup"><span data-stu-id="682aa-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="682aa-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="682aa-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="682aa-121">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="682aa-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="682aa-122">Набор разрешений для роли.</span><span class="sxs-lookup"><span data-stu-id="682aa-122">Permission set for the role.</span></span> <span data-ttu-id="682aa-123">Используемые биты:</span><span class="sxs-lookup"><span data-stu-id="682aa-123">The used bits are:</span></span> <br/>  <span data-ttu-id="682aa-124">2: имеет значение true, если роль может управлять узлов.</span><span class="sxs-lookup"><span data-stu-id="682aa-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="682aa-125">4: имеет значение true, если роль может создавать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="682aa-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="682aa-126">7: имеет значение true, если роль может присоединяться к комнате чата (или дочерним комнатам чата категории).</span><span class="sxs-lookup"><span data-stu-id="682aa-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="682aa-127">8: имеет значение true, если роль может общаться в комнате чата (или в дочерних комнатах чата категории).</span><span class="sxs-lookup"><span data-stu-id="682aa-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="682aa-128">10: имеет значение true, если роль может считывать журнал чата даже в том случае, если не подключен к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="682aa-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="682aa-129">11: имеет значение true, если роль может просматривать комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="682aa-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="682aa-130">(Это является дальнейшей уточнение по факторов, например, области и видимости.)</span><span class="sxs-lookup"><span data-stu-id="682aa-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="682aa-131">12: имеет значение true, если роль может общаться в чате аудитории.</span><span class="sxs-lookup"><span data-stu-id="682aa-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="682aa-132">13: имеет значение true, если роль может обходить правила видимости при просмотре узлов.</span><span class="sxs-lookup"><span data-stu-id="682aa-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="682aa-133">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="682aa-133">**Key**</span></span>

|<span data-ttu-id="682aa-134">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="682aa-134">**Column**</span></span>|<span data-ttu-id="682aa-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="682aa-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="682aa-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="682aa-136">rtypeID</span></span>  <br/> |<span data-ttu-id="682aa-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="682aa-137">Primary key.</span></span>  <br/> |
   

