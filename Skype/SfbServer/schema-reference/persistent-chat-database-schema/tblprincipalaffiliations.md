---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295316"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="92f95-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="92f95-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="92f95-104">ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.</span><span class="sxs-lookup"><span data-stu-id="92f95-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="92f95-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="92f95-105">**Columns**</span></span>

|<span data-ttu-id="92f95-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="92f95-106">**Column**</span></span>|<span data-ttu-id="92f95-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="92f95-107">**Type**</span></span>|<span data-ttu-id="92f95-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="92f95-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92f95-109">ПринЦипалид</span><span class="sxs-lookup"><span data-stu-id="92f95-109">principalID</span></span>  <br/> |<span data-ttu-id="92f95-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="92f95-110">int, not null</span></span>  <br/> |<span data-ttu-id="92f95-111">Идентификатор присоединенного участника.</span><span class="sxs-lookup"><span data-stu-id="92f95-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="92f95-112">Аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="92f95-112">affiliationID</span></span>  <br/> |<span data-ttu-id="92f95-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="92f95-113">int, not null</span></span>  <br/> |<span data-ttu-id="92f95-114">Идентификатор участника, представляющего назначение.</span><span class="sxs-lookup"><span data-stu-id="92f95-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="92f95-115">Каждый принципал (за исключением системных типов пользователей) также имеет свое Самоназначение.</span><span class="sxs-lookup"><span data-stu-id="92f95-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="92f95-116">индекса</span><span class="sxs-lookup"><span data-stu-id="92f95-116">index</span></span>  <br/> |<span data-ttu-id="92f95-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="92f95-117">int, not null</span></span>  <br/> |<span data-ttu-id="92f95-118">Индекса.</span><span class="sxs-lookup"><span data-stu-id="92f95-118">Index.</span></span> <span data-ttu-id="92f95-119">Значение для самостоятельных принадлежностей —-1, а для других — для других — в пределах от 1 в каждом \<ПринЦипалид, аффилиатионид\> сегмент.</span><span class="sxs-lookup"><span data-stu-id="92f95-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="92f95-120">Упдатедби</span><span class="sxs-lookup"><span data-stu-id="92f95-120">updatedBy</span></span>  <br/> |<span data-ttu-id="92f95-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="92f95-121">int, not null</span></span>  <br/> |<span data-ttu-id="92f95-122">Основной участник, который обновил Последнее обновление.</span><span class="sxs-lookup"><span data-stu-id="92f95-122">Principal that did the latest update.</span></span> <span data-ttu-id="92f95-123">Обычно это 1, что означает синхронизацию Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92f95-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="92f95-124">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="92f95-124">**Keys**</span></span>

|<span data-ttu-id="92f95-125">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="92f95-125">**Columns**</span></span>|<span data-ttu-id="92f95-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="92f95-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="92f95-127">\<ПринЦипалид, index, Аффилиатионид\></span><span class="sxs-lookup"><span data-stu-id="92f95-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="92f95-128">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="92f95-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="92f95-129">ПринЦипалид</span><span class="sxs-lookup"><span data-stu-id="92f95-129">principalID</span></span>  <br/> |<span data-ttu-id="92f95-130">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="92f95-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="92f95-131">Аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="92f95-131">affiliationID</span></span>  <br/> |<span data-ttu-id="92f95-132">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="92f95-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

