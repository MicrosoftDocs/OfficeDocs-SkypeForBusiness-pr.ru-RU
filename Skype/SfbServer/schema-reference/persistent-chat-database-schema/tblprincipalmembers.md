---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="08fb6-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="08fb6-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="08fb6-104">Таблица tblPrincipalMembers содержит сведения о членстве субъектов.</span><span class="sxs-lookup"><span data-stu-id="08fb6-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="08fb6-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="08fb6-105">**Columns**</span></span>

|<span data-ttu-id="08fb6-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="08fb6-106">**Column**</span></span>|<span data-ttu-id="08fb6-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="08fb6-107">**Type**</span></span>|<span data-ttu-id="08fb6-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="08fb6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08fb6-109">prinID</span><span class="sxs-lookup"><span data-stu-id="08fb6-109">prinID</span></span>  <br/> |<span data-ttu-id="08fb6-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="08fb6-110">int, not null</span></span>  <br/> |<span data-ttu-id="08fb6-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="08fb6-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="08fb6-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="08fb6-112">memberADPath</span></span>  <br/> |<span data-ttu-id="08fb6-113">nvarchar (384), отлично от null</span><span class="sxs-lookup"><span data-stu-id="08fb6-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="08fb6-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="08fb6-114">Distinguished name of a member.</span></span> <span data-ttu-id="08fb6-115">Член не нужно быть участником (в таблице tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="08fb6-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="08fb6-116">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="08fb6-116">**Keys**</span></span>

|<span data-ttu-id="08fb6-117">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="08fb6-117">**Column**</span></span>|<span data-ttu-id="08fb6-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="08fb6-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08fb6-119">\<prinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="08fb6-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="08fb6-120">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="08fb6-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="08fb6-121">prinID</span><span class="sxs-lookup"><span data-stu-id="08fb6-121">prinID</span></span>  <br/> |<span data-ttu-id="08fb6-122">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="08fb6-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

