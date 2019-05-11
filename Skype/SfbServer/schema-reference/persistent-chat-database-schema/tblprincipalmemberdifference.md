---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902238"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="d50bd-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="d50bd-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="d50bd-104">tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d50bd-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="d50bd-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="d50bd-105">**Columns**</span></span>

|<span data-ttu-id="d50bd-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d50bd-106">**Column**</span></span>|<span data-ttu-id="d50bd-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d50bd-107">**Type**</span></span>|<span data-ttu-id="d50bd-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d50bd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d50bd-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d50bd-109">prinGuid</span></span>  <br/> |<span data-ttu-id="d50bd-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="d50bd-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d50bd-111">GUID субъекта для измененной группы.</span><span class="sxs-lookup"><span data-stu-id="d50bd-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="d50bd-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="d50bd-112">memberADPath</span></span>  <br/> |<span data-ttu-id="d50bd-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d50bd-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="d50bd-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="d50bd-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="d50bd-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="d50bd-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="d50bd-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="d50bd-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d50bd-117">False, если элемент был добавлен.</span><span class="sxs-lookup"><span data-stu-id="d50bd-117">False if the member was added.</span></span> <span data-ttu-id="d50bd-118">Значение true, если элемент был удален.</span><span class="sxs-lookup"><span data-stu-id="d50bd-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="d50bd-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d50bd-119">**Key**</span></span>

|<span data-ttu-id="d50bd-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d50bd-120">**Column**</span></span>|<span data-ttu-id="d50bd-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d50bd-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d50bd-122">\<prinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="d50bd-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="d50bd-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="d50bd-123">Primary key.</span></span>  <br/> |
   

