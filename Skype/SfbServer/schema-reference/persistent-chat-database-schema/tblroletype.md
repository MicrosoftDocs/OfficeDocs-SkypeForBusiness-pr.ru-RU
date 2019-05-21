---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: Тблролетипе — это статическая таблица подстановки с типами ролей и связанными с ними наборами разрешений.
ms.openlocfilehash: 8d49e9f2c61b8672a01a9c77bcc825925a4e7b2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295218"
---
# <a name="tblroletype"></a><span data-ttu-id="c3197-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="c3197-103">tblRoleType</span></span>
 
<span data-ttu-id="c3197-104">Тблролетипе — это статическая таблица подстановки с типами ролей и связанными с ними наборами разрешений.</span><span class="sxs-lookup"><span data-stu-id="c3197-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="c3197-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="c3197-105">**Columns**</span></span>

|<span data-ttu-id="c3197-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c3197-106">**Column**</span></span>|<span data-ttu-id="c3197-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c3197-107">**Type**</span></span>|<span data-ttu-id="c3197-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3197-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3197-109">Ртипеид</span><span class="sxs-lookup"><span data-stu-id="c3197-109">rtypeID</span></span>  <br/> |<span data-ttu-id="c3197-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c3197-110">int, not null</span></span>  <br/> |<span data-ttu-id="c3197-111">Идентификатор типа роли.</span><span class="sxs-lookup"><span data-stu-id="c3197-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="c3197-112">Ртипедеск</span><span class="sxs-lookup"><span data-stu-id="c3197-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="c3197-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c3197-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="c3197-114">Описание типа роли.</span><span class="sxs-lookup"><span data-stu-id="c3197-114">Role type description.</span></span> <span data-ttu-id="c3197-115">Доступно четыре роли:</span><span class="sxs-lookup"><span data-stu-id="c3197-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="c3197-116">Член: участник комнаты чата</span><span class="sxs-lookup"><span data-stu-id="c3197-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="c3197-117">Руководитель: руководитель комнаты чата</span><span class="sxs-lookup"><span data-stu-id="c3197-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="c3197-118">Выставлено сообщение: выступающий для комнаты чата Аудиториум</span><span class="sxs-lookup"><span data-stu-id="c3197-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="c3197-119">Создатель: может создавать комнаты чата</span><span class="sxs-lookup"><span data-stu-id="c3197-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="c3197-120">Ртипеалловедпермсет</span><span class="sxs-lookup"><span data-stu-id="c3197-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="c3197-121">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c3197-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="c3197-122">Наборы разрешений для роли.</span><span class="sxs-lookup"><span data-stu-id="c3197-122">Permission set for the role.</span></span> <span data-ttu-id="c3197-123">Используются следующие биты:</span><span class="sxs-lookup"><span data-stu-id="c3197-123">The used bits are:</span></span> <br/>  <span data-ttu-id="c3197-124">2: значение true, если роль может управлять узлами.</span><span class="sxs-lookup"><span data-stu-id="c3197-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="c3197-125">4: значение true, если роль может создавать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="c3197-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="c3197-126">7: значение true, если роль может присоединиться к комнате чата (или дочерним комнатам чатов для категории).</span><span class="sxs-lookup"><span data-stu-id="c3197-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="c3197-127">8: true, если роль может общаться в комнате чата (или в дочерних комнатах чата).</span><span class="sxs-lookup"><span data-stu-id="c3197-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="c3197-128">10: true, если роль может читать историю чата, даже если она не присоединяется к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="c3197-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="c3197-129">11: true, если роль может видеть комнату чата.</span><span class="sxs-lookup"><span data-stu-id="c3197-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="c3197-130">(Это улучшено с помощью таких факторов, как область видимости и видимость.)</span><span class="sxs-lookup"><span data-stu-id="c3197-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="c3197-131">12: true, если роль может общаться в комнате чата Аудиториум.</span><span class="sxs-lookup"><span data-stu-id="c3197-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="c3197-132">13: true, если роль может обойти правила видимости при просмотре узлов.</span><span class="sxs-lookup"><span data-stu-id="c3197-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="c3197-133">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="c3197-133">**Key**</span></span>

|<span data-ttu-id="c3197-134">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c3197-134">**Column**</span></span>|<span data-ttu-id="c3197-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3197-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c3197-136">Ртипеид</span><span class="sxs-lookup"><span data-stu-id="c3197-136">rtypeID</span></span>  <br/> |<span data-ttu-id="c3197-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c3197-137">Primary key.</span></span>  <br/> |
   

