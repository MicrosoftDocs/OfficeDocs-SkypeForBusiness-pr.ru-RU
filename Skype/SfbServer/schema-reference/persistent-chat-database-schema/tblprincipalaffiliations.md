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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814477"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="7dea3-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="7dea3-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="7dea3-104">ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.</span><span class="sxs-lookup"><span data-stu-id="7dea3-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="7dea3-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="7dea3-105">**Columns**</span></span>

|<span data-ttu-id="7dea3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7dea3-106">**Column**</span></span>|<span data-ttu-id="7dea3-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7dea3-107">**Type**</span></span>|<span data-ttu-id="7dea3-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7dea3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7dea3-109">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="7dea3-109">principalID</span></span>  <br/> |<span data-ttu-id="7dea3-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7dea3-110">int, not null</span></span>  <br/> |<span data-ttu-id="7dea3-111">Идентификатор присоединенного участника.</span><span class="sxs-lookup"><span data-stu-id="7dea3-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="7dea3-112">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="7dea3-112">affiliationID</span></span>  <br/> |<span data-ttu-id="7dea3-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7dea3-113">int, not null</span></span>  <br/> |<span data-ttu-id="7dea3-114">Идентификатор участника, представляющего назначение.</span><span class="sxs-lookup"><span data-stu-id="7dea3-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="7dea3-115">Каждый принципал (за исключением системных типов пользователей) также имеет свое Самоназначение.</span><span class="sxs-lookup"><span data-stu-id="7dea3-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="7dea3-116">индекса</span><span class="sxs-lookup"><span data-stu-id="7dea3-116">index</span></span>  <br/> |<span data-ttu-id="7dea3-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7dea3-117">int, not null</span></span>  <br/> |<span data-ttu-id="7dea3-118">Индекса.</span><span class="sxs-lookup"><span data-stu-id="7dea3-118">Index.</span></span> <span data-ttu-id="7dea3-119">Значение для самостоятельных принадлежностей —-1, а для других — для других — в пределах от 1 в каждом \<ПринЦипалид, аффилиатионид\> сегмент.</span><span class="sxs-lookup"><span data-stu-id="7dea3-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="7dea3-120">упдатедби</span><span class="sxs-lookup"><span data-stu-id="7dea3-120">updatedBy</span></span>  <br/> |<span data-ttu-id="7dea3-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7dea3-121">int, not null</span></span>  <br/> |<span data-ttu-id="7dea3-122">Основной участник, который обновил Последнее обновление.</span><span class="sxs-lookup"><span data-stu-id="7dea3-122">Principal that did the latest update.</span></span> <span data-ttu-id="7dea3-123">Обычно это 1, что означает синхронизацию Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7dea3-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="7dea3-124">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="7dea3-124">**Keys**</span></span>

|<span data-ttu-id="7dea3-125">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="7dea3-125">**Columns**</span></span>|<span data-ttu-id="7dea3-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7dea3-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7dea3-127">\<ПринЦипалид, index, Аффилиатионид\></span><span class="sxs-lookup"><span data-stu-id="7dea3-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="7dea3-128">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7dea3-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7dea3-129">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="7dea3-129">principalID</span></span>  <br/> |<span data-ttu-id="7dea3-130">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="7dea3-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="7dea3-131">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="7dea3-131">affiliationID</span></span>  <br/> |<span data-ttu-id="7dea3-132">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="7dea3-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

