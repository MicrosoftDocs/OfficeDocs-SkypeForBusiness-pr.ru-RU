---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814077"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="f6dc3-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="f6dc3-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="f6dc3-104">ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6dc3-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="f6dc3-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="f6dc3-105">**Columns**</span></span>

|<span data-ttu-id="f6dc3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f6dc3-106">**Column**</span></span>|<span data-ttu-id="f6dc3-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f6dc3-107">**Type**</span></span>|<span data-ttu-id="f6dc3-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6dc3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6dc3-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="f6dc3-109">prinGuid</span></span>  <br/> |<span data-ttu-id="f6dc3-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="f6dc3-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f6dc3-111">Идентификатор GUID участника измененной группы.</span><span class="sxs-lookup"><span data-stu-id="f6dc3-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="f6dc3-112">мемберадпас</span><span class="sxs-lookup"><span data-stu-id="f6dc3-112">memberADPath</span></span>  <br/> |<span data-ttu-id="f6dc3-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f6dc3-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="f6dc3-114">Отличительное имя участника.</span><span class="sxs-lookup"><span data-stu-id="f6dc3-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="f6dc3-115">мемберремовед</span><span class="sxs-lookup"><span data-stu-id="f6dc3-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="f6dc3-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f6dc3-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f6dc3-117">Значение false, если элемент был добавлен.</span><span class="sxs-lookup"><span data-stu-id="f6dc3-117">False if the member was added.</span></span> <span data-ttu-id="f6dc3-118">Значение true, если элемент удален.</span><span class="sxs-lookup"><span data-stu-id="f6dc3-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="f6dc3-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="f6dc3-119">**Key**</span></span>

|<span data-ttu-id="f6dc3-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f6dc3-120">**Column**</span></span>|<span data-ttu-id="f6dc3-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6dc3-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6dc3-122">\<Прингуид, Мемберадпас\></span><span class="sxs-lookup"><span data-stu-id="f6dc3-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="f6dc3-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f6dc3-123">Primary key.</span></span>  <br/> |
   

