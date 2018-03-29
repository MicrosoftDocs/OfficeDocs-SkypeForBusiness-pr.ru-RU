---
title: tblPrincipalMemberDifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="ded23-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="ded23-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="ded23-104">tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ded23-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="ded23-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="ded23-105">**Columns**</span></span>

|<span data-ttu-id="ded23-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ded23-106">**Column**</span></span>|<span data-ttu-id="ded23-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ded23-107">**Type**</span></span>|<span data-ttu-id="ded23-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ded23-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ded23-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ded23-109">prinGuid</span></span>  <br/> |<span data-ttu-id="ded23-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="ded23-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="ded23-111">GUID субъекта для измененной группы.</span><span class="sxs-lookup"><span data-stu-id="ded23-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="ded23-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="ded23-112">memberADPath</span></span>  <br/> |<span data-ttu-id="ded23-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ded23-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="ded23-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="ded23-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="ded23-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="ded23-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="ded23-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="ded23-116">bit, not null</span></span>  <br/> |<span data-ttu-id="ded23-117">False, если элемент был добавлен.</span><span class="sxs-lookup"><span data-stu-id="ded23-117">False if the member was added.</span></span> <span data-ttu-id="ded23-118">Значение true, если элемент был удален.</span><span class="sxs-lookup"><span data-stu-id="ded23-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="ded23-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ded23-119">**Key**</span></span>

|<span data-ttu-id="ded23-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ded23-120">**Column**</span></span>|<span data-ttu-id="ded23-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ded23-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ded23-122">\<prinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="ded23-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="ded23-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="ded23-123">Primary key.</span></span>  <br/> |
   

