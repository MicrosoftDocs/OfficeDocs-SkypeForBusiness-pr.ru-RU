---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813577"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="5bdc3-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="5bdc3-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="5bdc3-104">ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="5bdc3-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="5bdc3-105">**Columns**</span></span>

|<span data-ttu-id="5bdc3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5bdc3-106">**Column**</span></span>|<span data-ttu-id="5bdc3-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5bdc3-107">**Type**</span></span>|<span data-ttu-id="5bdc3-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5bdc3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5bdc3-109">принид</span><span class="sxs-lookup"><span data-stu-id="5bdc3-109">prinID</span></span>  <br/> |<span data-ttu-id="5bdc3-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5bdc3-110">int, not null</span></span>  <br/> |<span data-ttu-id="5bdc3-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5bdc3-112">принаффилиатионсдирти</span><span class="sxs-lookup"><span data-stu-id="5bdc3-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="5bdc3-113">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5bdc3-113">bit, not null</span></span>  <br/> |<span data-ttu-id="5bdc3-114">Значение true, если присвоить участникам участники необходимо обновлять.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="5bdc3-115">принаттрибутесдирти</span><span class="sxs-lookup"><span data-stu-id="5bdc3-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="5bdc3-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5bdc3-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5bdc3-117">Значение true, если атрибуты участника нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="5bdc3-118">принделетед</span><span class="sxs-lookup"><span data-stu-id="5bdc3-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="5bdc3-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5bdc3-119">bit, not null</span></span>  <br/> |<span data-ttu-id="5bdc3-120">Значение true, если участник удален.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="5bdc3-121">трикаунт</span><span class="sxs-lookup"><span data-stu-id="5bdc3-121">tryCount</span></span>  <br/> |<span data-ttu-id="5bdc3-122">целое</span><span class="sxs-lookup"><span data-stu-id="5bdc3-122">int</span></span>  <br/> |<span data-ttu-id="5bdc3-123">Количество попыток обновления участника из доменных служб Active Directory, произошедших в данный момент.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="5bdc3-124">ласттри</span><span class="sxs-lookup"><span data-stu-id="5bdc3-124">lastTry</span></span>  <br/> |<span data-ttu-id="5bdc3-125">datetime</span><span class="sxs-lookup"><span data-stu-id="5bdc3-125">datetime</span></span>  <br/> |<span data-ttu-id="5bdc3-126">Метка времени последней попытки обновить участника.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="5bdc3-127">Может иметь значение null, если вы еще не пытались обновить обновление.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="5bdc3-128">нексттри</span><span class="sxs-lookup"><span data-stu-id="5bdc3-128">nextTry</span></span>  <br/> |<span data-ttu-id="5bdc3-129">datetime</span><span class="sxs-lookup"><span data-stu-id="5bdc3-129">datetime</span></span>  <br/> |<span data-ttu-id="5bdc3-130">Метка времени для следующего запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="5bdc3-131">Может иметь значение null, если дальнейшее обновление не запланировано.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="5bdc3-132">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="5bdc3-132">**Keys**</span></span>

|<span data-ttu-id="5bdc3-133">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5bdc3-133">**Column**</span></span>|<span data-ttu-id="5bdc3-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5bdc3-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5bdc3-135">принид</span><span class="sxs-lookup"><span data-stu-id="5bdc3-135">prinID</span></span>  <br/> |<span data-ttu-id="5bdc3-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5bdc3-137">принид</span><span class="sxs-lookup"><span data-stu-id="5bdc3-137">prinID</span></span>  <br/> |<span data-ttu-id="5bdc3-138">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="5bdc3-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

