---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904162"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="471a0-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="471a0-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="471a0-104">Таблица tblPrincipalMembers содержит сведения о членстве субъектов.</span><span class="sxs-lookup"><span data-stu-id="471a0-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="471a0-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="471a0-105">**Columns**</span></span>

|<span data-ttu-id="471a0-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="471a0-106">**Column**</span></span>|<span data-ttu-id="471a0-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="471a0-107">**Type**</span></span>|<span data-ttu-id="471a0-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="471a0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="471a0-109">prinID</span><span class="sxs-lookup"><span data-stu-id="471a0-109">prinID</span></span>  <br/> |<span data-ttu-id="471a0-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="471a0-110">int, not null</span></span>  <br/> |<span data-ttu-id="471a0-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="471a0-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="471a0-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="471a0-112">memberADPath</span></span>  <br/> |<span data-ttu-id="471a0-113">nvarchar (384), отлично от null</span><span class="sxs-lookup"><span data-stu-id="471a0-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="471a0-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="471a0-114">Distinguished name of a member.</span></span> <span data-ttu-id="471a0-115">Член не нужно быть участником (в таблице tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="471a0-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="471a0-116">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="471a0-116">**Keys**</span></span>

|<span data-ttu-id="471a0-117">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="471a0-117">**Column**</span></span>|<span data-ttu-id="471a0-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="471a0-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="471a0-119">\<prinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="471a0-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="471a0-120">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="471a0-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="471a0-121">prinID</span><span class="sxs-lookup"><span data-stu-id="471a0-121">prinID</span></span>  <br/> |<span data-ttu-id="471a0-122">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="471a0-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

