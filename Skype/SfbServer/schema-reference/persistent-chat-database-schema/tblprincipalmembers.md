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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: ТблпринЦипалмемберс включает участников участника.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813947"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="a53f0-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="a53f0-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="a53f0-104">ТблпринЦипалмемберс включает участников участника.</span><span class="sxs-lookup"><span data-stu-id="a53f0-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="a53f0-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="a53f0-105">**Columns**</span></span>

|<span data-ttu-id="a53f0-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a53f0-106">**Column**</span></span>|<span data-ttu-id="a53f0-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a53f0-107">**Type**</span></span>|<span data-ttu-id="a53f0-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a53f0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a53f0-109">принид</span><span class="sxs-lookup"><span data-stu-id="a53f0-109">prinID</span></span>  <br/> |<span data-ttu-id="a53f0-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a53f0-110">int, not null</span></span>  <br/> |<span data-ttu-id="a53f0-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="a53f0-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a53f0-112">мемберадпас</span><span class="sxs-lookup"><span data-stu-id="a53f0-112">memberADPath</span></span>  <br/> |<span data-ttu-id="a53f0-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a53f0-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a53f0-114">Отличительное имя участника.</span><span class="sxs-lookup"><span data-stu-id="a53f0-114">Distinguished name of a member.</span></span> <span data-ttu-id="a53f0-115">Участник может не быть участником (в таблице ТблпринЦипал).</span><span class="sxs-lookup"><span data-stu-id="a53f0-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="a53f0-116">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="a53f0-116">**Keys**</span></span>

|<span data-ttu-id="a53f0-117">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a53f0-117">**Column**</span></span>|<span data-ttu-id="a53f0-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a53f0-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a53f0-119">\<Принид, Мемберадпас\></span><span class="sxs-lookup"><span data-stu-id="a53f0-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="a53f0-120">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a53f0-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a53f0-121">принид</span><span class="sxs-lookup"><span data-stu-id="a53f0-121">prinID</span></span>  <br/> |<span data-ttu-id="a53f0-122">Внешний ключ с подстановкой в ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="a53f0-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

