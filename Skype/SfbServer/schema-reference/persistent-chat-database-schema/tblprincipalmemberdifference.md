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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295302"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="1f7a2-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="1f7a2-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="1f7a2-104">ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f7a2-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="1f7a2-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="1f7a2-105">**Columns**</span></span>

|<span data-ttu-id="1f7a2-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1f7a2-106">**Column**</span></span>|<span data-ttu-id="1f7a2-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="1f7a2-107">**Type**</span></span>|<span data-ttu-id="1f7a2-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1f7a2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f7a2-109">Прингуид</span><span class="sxs-lookup"><span data-stu-id="1f7a2-109">prinGuid</span></span>  <br/> |<span data-ttu-id="1f7a2-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="1f7a2-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="1f7a2-111">Идентификатор GUID участника измененной группы.</span><span class="sxs-lookup"><span data-stu-id="1f7a2-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="1f7a2-112">Мемберадпас</span><span class="sxs-lookup"><span data-stu-id="1f7a2-112">memberADPath</span></span>  <br/> |<span data-ttu-id="1f7a2-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1f7a2-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="1f7a2-114">Отличительное имя участника.</span><span class="sxs-lookup"><span data-stu-id="1f7a2-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="1f7a2-115">Мемберремовед</span><span class="sxs-lookup"><span data-stu-id="1f7a2-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="1f7a2-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1f7a2-116">bit, not null</span></span>  <br/> |<span data-ttu-id="1f7a2-117">Значение false, если элемент был добавлен.</span><span class="sxs-lookup"><span data-stu-id="1f7a2-117">False if the member was added.</span></span> <span data-ttu-id="1f7a2-118">Значение true, если элемент удален.</span><span class="sxs-lookup"><span data-stu-id="1f7a2-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="1f7a2-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="1f7a2-119">**Key**</span></span>

|<span data-ttu-id="1f7a2-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1f7a2-120">**Column**</span></span>|<span data-ttu-id="1f7a2-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1f7a2-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f7a2-122">\<Прингуид, Мемберадпас\></span><span class="sxs-lookup"><span data-stu-id="1f7a2-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="1f7a2-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="1f7a2-123">Primary key.</span></span>  <br/> |
   

