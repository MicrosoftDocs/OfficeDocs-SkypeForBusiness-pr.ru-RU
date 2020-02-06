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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: Тблролетипе — это статическая таблица подстановки с типами ролей и связанными с ними наборами разрешений.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812907"
---
# <a name="tblroletype"></a><span data-ttu-id="9433b-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="9433b-103">tblRoleType</span></span>
 
<span data-ttu-id="9433b-104">Тблролетипе — это статическая таблица подстановки с типами ролей и связанными с ними наборами разрешений.</span><span class="sxs-lookup"><span data-stu-id="9433b-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="9433b-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="9433b-105">**Columns**</span></span>

|<span data-ttu-id="9433b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9433b-106">**Column**</span></span>|<span data-ttu-id="9433b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9433b-107">**Type**</span></span>|<span data-ttu-id="9433b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9433b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9433b-109">ртипеид</span><span class="sxs-lookup"><span data-stu-id="9433b-109">rtypeID</span></span>  <br/> |<span data-ttu-id="9433b-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9433b-110">int, not null</span></span>  <br/> |<span data-ttu-id="9433b-111">Идентификатор типа роли.</span><span class="sxs-lookup"><span data-stu-id="9433b-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="9433b-112">ртипедеск</span><span class="sxs-lookup"><span data-stu-id="9433b-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="9433b-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9433b-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="9433b-114">Описание типа роли.</span><span class="sxs-lookup"><span data-stu-id="9433b-114">Role type description.</span></span> <span data-ttu-id="9433b-115">Доступно четыре роли:</span><span class="sxs-lookup"><span data-stu-id="9433b-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="9433b-116">Член: участник комнаты чата</span><span class="sxs-lookup"><span data-stu-id="9433b-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="9433b-117">Руководитель: руководитель комнаты чата</span><span class="sxs-lookup"><span data-stu-id="9433b-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="9433b-118">Выставлено сообщение: выступающий для комнаты чата Аудиториум</span><span class="sxs-lookup"><span data-stu-id="9433b-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="9433b-119">Создатель: может создавать комнаты чата</span><span class="sxs-lookup"><span data-stu-id="9433b-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="9433b-120">ртипеалловедпермсет</span><span class="sxs-lookup"><span data-stu-id="9433b-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="9433b-121">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9433b-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="9433b-122">Наборы разрешений для роли.</span><span class="sxs-lookup"><span data-stu-id="9433b-122">Permission set for the role.</span></span> <span data-ttu-id="9433b-123">Используются следующие биты:</span><span class="sxs-lookup"><span data-stu-id="9433b-123">The used bits are:</span></span> <br/>  <span data-ttu-id="9433b-124">2: значение true, если роль может управлять узлами.</span><span class="sxs-lookup"><span data-stu-id="9433b-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="9433b-125">4: значение true, если роль может создавать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="9433b-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="9433b-126">7: значение true, если роль может присоединиться к комнате чата (или дочерним комнатам чатов для категории).</span><span class="sxs-lookup"><span data-stu-id="9433b-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9433b-127">8: true, если роль может общаться в комнате чата (или в дочерних комнатах чата).</span><span class="sxs-lookup"><span data-stu-id="9433b-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9433b-128">10: true, если роль может читать историю чата, даже если она не присоединяется к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="9433b-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="9433b-129">11: true, если роль может видеть комнату чата.</span><span class="sxs-lookup"><span data-stu-id="9433b-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="9433b-130">(Это улучшено с помощью таких факторов, как область видимости и видимость.)</span><span class="sxs-lookup"><span data-stu-id="9433b-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="9433b-131">12: true, если роль может общаться в комнате чата Аудиториум.</span><span class="sxs-lookup"><span data-stu-id="9433b-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="9433b-132">13: true, если роль может обойти правила видимости при просмотре узлов.</span><span class="sxs-lookup"><span data-stu-id="9433b-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="9433b-133">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="9433b-133">**Key**</span></span>

|<span data-ttu-id="9433b-134">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9433b-134">**Column**</span></span>|<span data-ttu-id="9433b-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9433b-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9433b-136">ртипеид</span><span class="sxs-lookup"><span data-stu-id="9433b-136">rtypeID</span></span>  <br/> |<span data-ttu-id="9433b-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="9433b-137">Primary key.</span></span>  <br/> |
   

