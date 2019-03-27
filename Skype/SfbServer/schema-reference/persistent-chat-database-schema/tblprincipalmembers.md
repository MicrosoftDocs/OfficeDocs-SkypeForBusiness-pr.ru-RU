---
title: tblPrincipalMembers
ms.reviewer: ''
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
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874254"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="7c651-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="7c651-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="7c651-104">Таблица tblPrincipalMembers содержит сведения о членстве субъектов.</span><span class="sxs-lookup"><span data-stu-id="7c651-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="7c651-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="7c651-105">**Columns**</span></span>

|<span data-ttu-id="7c651-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7c651-106">**Column**</span></span>|<span data-ttu-id="7c651-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7c651-107">**Type**</span></span>|<span data-ttu-id="7c651-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="7c651-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7c651-109">prinID</span><span class="sxs-lookup"><span data-stu-id="7c651-109">prinID</span></span>  <br/> |<span data-ttu-id="7c651-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="7c651-110">int, not null</span></span>  <br/> |<span data-ttu-id="7c651-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="7c651-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="7c651-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="7c651-112">memberADPath</span></span>  <br/> |<span data-ttu-id="7c651-113">nvarchar (384), отлично от null</span><span class="sxs-lookup"><span data-stu-id="7c651-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="7c651-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="7c651-114">Distinguished name of a member.</span></span> <span data-ttu-id="7c651-115">Член не нужно быть участником (в таблице tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="7c651-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="7c651-116">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="7c651-116">**Keys**</span></span>

|<span data-ttu-id="7c651-117">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7c651-117">**Column**</span></span>|<span data-ttu-id="7c651-118">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="7c651-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c651-119">\<prinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="7c651-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="7c651-120">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7c651-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7c651-121">prinID</span><span class="sxs-lookup"><span data-stu-id="7c651-121">prinID</span></span>  <br/> |<span data-ttu-id="7c651-122">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="7c651-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

