---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations содержит членство в расположениях, включая группы безопасности доменных служб Active Directory, в контейнерах Active Directory, в доменах.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815869"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="7867c-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="7867c-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="7867c-104">tblPrincipalAffiliations содержит членство в расположениях, включая группы безопасности доменных служб Active Directory, в контейнерах Active Directory, в доменах.</span><span class="sxs-lookup"><span data-stu-id="7867c-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="7867c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="7867c-105">**Columns**</span></span>

|<span data-ttu-id="7867c-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7867c-106">**Column**</span></span>|<span data-ttu-id="7867c-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7867c-107">**Type**</span></span>|<span data-ttu-id="7867c-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7867c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7867c-109">principalID</span><span class="sxs-lookup"><span data-stu-id="7867c-109">principalID</span></span>  <br/> |<span data-ttu-id="7867c-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7867c-110">int, not null</span></span>  <br/> |<span data-ttu-id="7867c-111">Идентификатор присоединенного субъекта.</span><span class="sxs-lookup"><span data-stu-id="7867c-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="7867c-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="7867c-112">affiliationID</span></span>  <br/> |<span data-ttu-id="7867c-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7867c-113">int, not null</span></span>  <br/> |<span data-ttu-id="7867c-p101">Идентификатор субъекта, представляющего присоединение. Каждый субъект (за исключением типов пользователей системы) также присоединен сам к себе.</span><span class="sxs-lookup"><span data-stu-id="7867c-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="7867c-116">index</span><span class="sxs-lookup"><span data-stu-id="7867c-116">index</span></span>  <br/> |<span data-ttu-id="7867c-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7867c-117">int, not null</span></span>  <br/> |<span data-ttu-id="7867c-118">Индекс.</span><span class="sxs-lookup"><span data-stu-id="7867c-118">Index.</span></span> <span data-ttu-id="7867c-119">Значение для самостоятельного присоединения — -1, а для других присоединений оно последовательно увеличивается с 1 в каждом \<principalID, affiliationId\> сегменте.</span><span class="sxs-lookup"><span data-stu-id="7867c-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="7867c-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="7867c-120">updatedBy</span></span>  <br/> |<span data-ttu-id="7867c-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7867c-121">int, not null</span></span>  <br/> |<span data-ttu-id="7867c-p103">Субъект, выполнивший последнее обновление. Обычно это 1, что означает синхронизацию с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7867c-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="7867c-124">**Keys**</span><span class="sxs-lookup"><span data-stu-id="7867c-124">**Keys**</span></span>

|<span data-ttu-id="7867c-125">**Columns**</span><span class="sxs-lookup"><span data-stu-id="7867c-125">**Columns**</span></span>|<span data-ttu-id="7867c-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7867c-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="7867c-127">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7867c-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7867c-128">principalID</span><span class="sxs-lookup"><span data-stu-id="7867c-128">principalID</span></span>  <br/> |<span data-ttu-id="7867c-129">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="7867c-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="7867c-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="7867c-130">affiliationID</span></span>  <br/> |<span data-ttu-id="7867c-131">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="7867c-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

