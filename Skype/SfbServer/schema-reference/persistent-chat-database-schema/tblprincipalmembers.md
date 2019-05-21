---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: ТблпринЦипалмемберс включает участников участника.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295288"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="19beb-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="19beb-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="19beb-104">ТблпринЦипалмемберс включает участников участника.</span><span class="sxs-lookup"><span data-stu-id="19beb-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="19beb-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="19beb-105">**Columns**</span></span>

|<span data-ttu-id="19beb-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="19beb-106">**Column**</span></span>|<span data-ttu-id="19beb-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="19beb-107">**Type**</span></span>|<span data-ttu-id="19beb-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="19beb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19beb-109">Принид</span><span class="sxs-lookup"><span data-stu-id="19beb-109">prinID</span></span>  <br/> |<span data-ttu-id="19beb-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="19beb-110">int, not null</span></span>  <br/> |<span data-ttu-id="19beb-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="19beb-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="19beb-112">Мемберадпас</span><span class="sxs-lookup"><span data-stu-id="19beb-112">memberADPath</span></span>  <br/> |<span data-ttu-id="19beb-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="19beb-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="19beb-114">Отличительное имя участника.</span><span class="sxs-lookup"><span data-stu-id="19beb-114">Distinguished name of a member.</span></span> <span data-ttu-id="19beb-115">Участник может не быть участником (в таблице ТблпринЦипал).</span><span class="sxs-lookup"><span data-stu-id="19beb-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="19beb-116">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="19beb-116">**Keys**</span></span>

|<span data-ttu-id="19beb-117">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="19beb-117">**Column**</span></span>|<span data-ttu-id="19beb-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="19beb-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="19beb-119">\<Принид, Мемберадпас\></span><span class="sxs-lookup"><span data-stu-id="19beb-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="19beb-120">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="19beb-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="19beb-121">Принид</span><span class="sxs-lookup"><span data-stu-id="19beb-121">prinID</span></span>  <br/> |<span data-ttu-id="19beb-122">Внешний ключ с подстановкой в ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="19beb-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

