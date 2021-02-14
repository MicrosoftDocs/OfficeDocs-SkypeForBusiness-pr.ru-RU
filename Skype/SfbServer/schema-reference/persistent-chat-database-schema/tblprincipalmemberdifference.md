---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference содержит изменения членства в группах (как добавленных, так и удаленных членов), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809709"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="f29fa-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="f29fa-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="f29fa-104">tblPrincipalMemberDifference содержит изменения членства в группах (как добавленных, так и удаленных членов), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f29fa-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="f29fa-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="f29fa-105">**Columns**</span></span>

|<span data-ttu-id="f29fa-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f29fa-106">**Column**</span></span>|<span data-ttu-id="f29fa-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f29fa-107">**Type**</span></span>|<span data-ttu-id="f29fa-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f29fa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f29fa-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f29fa-109">prinGuid</span></span>  <br/> |<span data-ttu-id="f29fa-110">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="f29fa-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f29fa-111">GUID субъекта для измененной группы.</span><span class="sxs-lookup"><span data-stu-id="f29fa-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="f29fa-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="f29fa-112">memberADPath</span></span>  <br/> |<span data-ttu-id="f29fa-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f29fa-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="f29fa-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="f29fa-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="f29fa-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="f29fa-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="f29fa-116">bit, не NULL</span><span class="sxs-lookup"><span data-stu-id="f29fa-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f29fa-p101">False, если член был добавлен. True, если член был удален.</span><span class="sxs-lookup"><span data-stu-id="f29fa-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="f29fa-119">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="f29fa-119">**Key**</span></span>

|<span data-ttu-id="f29fa-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f29fa-120">**Column**</span></span>|<span data-ttu-id="f29fa-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f29fa-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="f29fa-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f29fa-122">Primary key.</span></span>  <br/> |
   

