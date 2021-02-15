---
title: tblRoleType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType — это статическая таблица подстановки с типами ролей и сопоставленными с ними наборами разрешений.
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831529"
---
# <a name="tblroletype"></a><span data-ttu-id="5c075-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="5c075-103">tblRoleType</span></span>
 
<span data-ttu-id="5c075-104">tblRoleType — это статическая таблица подстановки с типами ролей и сопоставленными с ними наборами разрешений.</span><span class="sxs-lookup"><span data-stu-id="5c075-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="5c075-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="5c075-105">**Columns**</span></span>

|<span data-ttu-id="5c075-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5c075-106">**Column**</span></span>|<span data-ttu-id="5c075-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5c075-107">**Type**</span></span>|<span data-ttu-id="5c075-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5c075-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c075-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="5c075-109">rtypeID</span></span>  <br/> |<span data-ttu-id="5c075-110">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="5c075-110">int, not null</span></span>  <br/> |<span data-ttu-id="5c075-111">Идентификатор типа роли.</span><span class="sxs-lookup"><span data-stu-id="5c075-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="5c075-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="5c075-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="5c075-113">nvarchar (256), не NULL</span><span class="sxs-lookup"><span data-stu-id="5c075-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="5c075-p101">Описание типа роли. Доступно четыре роли:</span><span class="sxs-lookup"><span data-stu-id="5c075-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="5c075-116">Member: член комнаты чата</span><span class="sxs-lookup"><span data-stu-id="5c075-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="5c075-117">Manager: руководитель комнаты чата</span><span class="sxs-lookup"><span data-stu-id="5c075-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="5c075-118">Voiced: выступающий для аудиторной комнаты чата</span><span class="sxs-lookup"><span data-stu-id="5c075-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="5c075-119">Creator: человек, который может создавать комнаты чата</span><span class="sxs-lookup"><span data-stu-id="5c075-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="5c075-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="5c075-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="5c075-121">bigint, не NULL</span><span class="sxs-lookup"><span data-stu-id="5c075-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="5c075-p102">Набор разрешений для роли. Используются следующие биты:</span><span class="sxs-lookup"><span data-stu-id="5c075-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="5c075-124">2: True if the role can manage nodes.</span><span class="sxs-lookup"><span data-stu-id="5c075-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="5c075-125">4: имеет значение true, если роль может создавать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="5c075-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="5c075-126">7: имеет значение true, если роль может присоединяться к комнате чата (или дочерним комнатам чата категории).</span><span class="sxs-lookup"><span data-stu-id="5c075-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="5c075-127">8: имеет значение true, если роль может общаться с помощью чата в комнате чата (или в дочерних комнатах чата категории).</span><span class="sxs-lookup"><span data-stu-id="5c075-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="5c075-128">10: имеет значение true, если роль может считывать журнал чата даже без присоединения к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="5c075-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="5c075-p103">11: имеет значение true, если роль может просматривать комнату чата. (Данная возможность дополнительно уточняется различными факторами, такими как область и видимость.)</span><span class="sxs-lookup"><span data-stu-id="5c075-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="5c075-131">12: имеет значение true, если роль может общаться с помощью чата в аудиторной комнате чата.</span><span class="sxs-lookup"><span data-stu-id="5c075-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="5c075-132">13: имеет значение true, если роль может обходить правила видимости при просмотре узлов.</span><span class="sxs-lookup"><span data-stu-id="5c075-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="5c075-133">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="5c075-133">**Key**</span></span>

|<span data-ttu-id="5c075-134">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5c075-134">**Column**</span></span>|<span data-ttu-id="5c075-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5c075-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c075-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="5c075-136">rtypeID</span></span>  <br/> |<span data-ttu-id="5c075-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5c075-137">Primary key.</span></span>  <br/> |
   

