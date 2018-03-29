---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: Таблица tblPrincipalAffiliations содержит присоединения субъектов, которые описывают членство в расположениях, включая группы безопасности доменных служб Active Directory, контейнеры Active Directory и доменов.
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="5b73d-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="5b73d-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="5b73d-104">Таблица tblPrincipalAffiliations содержит присоединения субъектов, которые описывают членство в расположениях, включая группы безопасности доменных служб Active Directory, контейнеры Active Directory и доменов.</span><span class="sxs-lookup"><span data-stu-id="5b73d-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="5b73d-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="5b73d-105">**Columns**</span></span>

|<span data-ttu-id="5b73d-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5b73d-106">**Column**</span></span>|<span data-ttu-id="5b73d-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5b73d-107">**Type**</span></span>|<span data-ttu-id="5b73d-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5b73d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5b73d-109">principalID</span><span class="sxs-lookup"><span data-stu-id="5b73d-109">principalID</span></span>  <br/> |<span data-ttu-id="5b73d-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="5b73d-110">int, not null</span></span>  <br/> |<span data-ttu-id="5b73d-111">Идентификатор присоединенного субъекта.</span><span class="sxs-lookup"><span data-stu-id="5b73d-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="5b73d-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="5b73d-112">affiliationID</span></span>  <br/> |<span data-ttu-id="5b73d-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="5b73d-113">int, not null</span></span>  <br/> |<span data-ttu-id="5b73d-114">Идентификатор участника, представляющий принадлежность.</span><span class="sxs-lookup"><span data-stu-id="5b73d-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="5b73d-115">Каждый участник (за исключением системы--пользователем) имеет также самораспаковывающийся принадлежность к.</span><span class="sxs-lookup"><span data-stu-id="5b73d-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="5b73d-116">Индекс</span><span class="sxs-lookup"><span data-stu-id="5b73d-116">index</span></span>  <br/> |<span data-ttu-id="5b73d-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="5b73d-117">int, not null</span></span>  <br/> |<span data-ttu-id="5b73d-118">Индекс.</span><span class="sxs-lookup"><span data-stu-id="5b73d-118">Index.</span></span> <span data-ttu-id="5b73d-119">Для назначения самораспаковывающийся значение -1, а для других принадлежности его последовательно увеличивается от 1 в каждой \<principalID affiliationId\> интервалов.</span><span class="sxs-lookup"><span data-stu-id="5b73d-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="5b73d-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="5b73d-120">updatedBy</span></span>  <br/> |<span data-ttu-id="5b73d-121">int, не null</span><span class="sxs-lookup"><span data-stu-id="5b73d-121">int, not null</span></span>  <br/> |<span data-ttu-id="5b73d-122">Участник, который выполнил последнее обновление.</span><span class="sxs-lookup"><span data-stu-id="5b73d-122">Principal that did the latest update.</span></span> <span data-ttu-id="5b73d-123">Обычно это 1, что означает синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b73d-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="5b73d-124">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="5b73d-124">**Keys**</span></span>

|<span data-ttu-id="5b73d-125">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="5b73d-125">**Columns**</span></span>|<span data-ttu-id="5b73d-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5b73d-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b73d-127">\<principalID, индекса, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="5b73d-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="5b73d-128">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5b73d-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5b73d-129">principalID</span><span class="sxs-lookup"><span data-stu-id="5b73d-129">principalID</span></span>  <br/> |<span data-ttu-id="5b73d-130">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="5b73d-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="5b73d-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="5b73d-131">affiliationID</span></span>  <br/> |<span data-ttu-id="5b73d-132">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="5b73d-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

