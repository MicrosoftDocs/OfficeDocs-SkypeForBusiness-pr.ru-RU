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
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295260"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="f7486-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="f7486-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="f7486-104">ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f7486-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="f7486-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="f7486-105">**Columns**</span></span>

|<span data-ttu-id="f7486-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f7486-106">**Column**</span></span>|<span data-ttu-id="f7486-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f7486-107">**Type**</span></span>|<span data-ttu-id="f7486-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f7486-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7486-109">Принид</span><span class="sxs-lookup"><span data-stu-id="f7486-109">prinID</span></span>  <br/> |<span data-ttu-id="f7486-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f7486-110">int, not null</span></span>  <br/> |<span data-ttu-id="f7486-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="f7486-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f7486-112">Принаффилиатионсдирти</span><span class="sxs-lookup"><span data-stu-id="f7486-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="f7486-113">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f7486-113">bit, not null</span></span>  <br/> |<span data-ttu-id="f7486-114">Значение true, если присвоить участникам участники необходимо обновлять.</span><span class="sxs-lookup"><span data-stu-id="f7486-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f7486-115">Принаттрибутесдирти</span><span class="sxs-lookup"><span data-stu-id="f7486-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="f7486-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f7486-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f7486-117">Значение true, если атрибуты участника нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="f7486-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f7486-118">Принделетед</span><span class="sxs-lookup"><span data-stu-id="f7486-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="f7486-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f7486-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f7486-120">Значение true, если участник удален.</span><span class="sxs-lookup"><span data-stu-id="f7486-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="f7486-121">Трикаунт</span><span class="sxs-lookup"><span data-stu-id="f7486-121">tryCount</span></span>  <br/> |<span data-ttu-id="f7486-122">целое</span><span class="sxs-lookup"><span data-stu-id="f7486-122">int</span></span>  <br/> |<span data-ttu-id="f7486-123">Количество попыток обновления участника из доменных служб Active Directory, произошедших в данный момент.</span><span class="sxs-lookup"><span data-stu-id="f7486-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="f7486-124">Ласттри</span><span class="sxs-lookup"><span data-stu-id="f7486-124">lastTry</span></span>  <br/> |<span data-ttu-id="f7486-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f7486-125">datetime</span></span>  <br/> |<span data-ttu-id="f7486-126">Метка времени последней попытки обновить участника.</span><span class="sxs-lookup"><span data-stu-id="f7486-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="f7486-127">Может иметь значение null, если вы еще не пытались обновить обновление.</span><span class="sxs-lookup"><span data-stu-id="f7486-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="f7486-128">Нексттри</span><span class="sxs-lookup"><span data-stu-id="f7486-128">nextTry</span></span>  <br/> |<span data-ttu-id="f7486-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f7486-129">datetime</span></span>  <br/> |<span data-ttu-id="f7486-130">Метка времени для следующего запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="f7486-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="f7486-131">Может иметь значение null, если дальнейшее обновление не запланировано.</span><span class="sxs-lookup"><span data-stu-id="f7486-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="f7486-132">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="f7486-132">**Keys**</span></span>

|<span data-ttu-id="f7486-133">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f7486-133">**Column**</span></span>|<span data-ttu-id="f7486-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f7486-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f7486-135">Принид</span><span class="sxs-lookup"><span data-stu-id="f7486-135">prinID</span></span>  <br/> |<span data-ttu-id="f7486-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f7486-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f7486-137">Принид</span><span class="sxs-lookup"><span data-stu-id="f7486-137">prinID</span></span>  <br/> |<span data-ttu-id="f7486-138">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="f7486-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

