---
title: tblPrincipalMemberDifference
ms.reviewer: ''
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
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212448"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="94e08-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="94e08-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="94e08-104">tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94e08-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="94e08-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="94e08-105">**Columns**</span></span>

|<span data-ttu-id="94e08-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="94e08-106">**Column**</span></span>|<span data-ttu-id="94e08-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="94e08-107">**Type**</span></span>|<span data-ttu-id="94e08-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="94e08-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94e08-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="94e08-109">prinGuid</span></span>  <br/> |<span data-ttu-id="94e08-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="94e08-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="94e08-111">GUID субъекта для измененной группы.</span><span class="sxs-lookup"><span data-stu-id="94e08-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="94e08-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="94e08-112">memberADPath</span></span>  <br/> |<span data-ttu-id="94e08-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="94e08-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="94e08-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="94e08-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="94e08-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="94e08-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="94e08-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="94e08-116">bit, not null</span></span>  <br/> |<span data-ttu-id="94e08-117">False, если элемент был добавлен.</span><span class="sxs-lookup"><span data-stu-id="94e08-117">False if the member was added.</span></span> <span data-ttu-id="94e08-118">Значение true, если элемент был удален.</span><span class="sxs-lookup"><span data-stu-id="94e08-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="94e08-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="94e08-119">**Key**</span></span>

|<span data-ttu-id="94e08-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="94e08-120">**Column**</span></span>|<span data-ttu-id="94e08-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="94e08-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="94e08-122">\<prinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="94e08-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="94e08-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="94e08-123">Primary key.</span></span>  <br/> |
   

