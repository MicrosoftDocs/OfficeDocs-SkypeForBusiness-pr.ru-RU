---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831599"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="28d06-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="28d06-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="28d06-104">Таблица tblPrincipalMembers содержит сведения о членстве субъектов.</span><span class="sxs-lookup"><span data-stu-id="28d06-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="28d06-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="28d06-105">**Columns**</span></span>

|<span data-ttu-id="28d06-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="28d06-106">**Column**</span></span>|<span data-ttu-id="28d06-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="28d06-107">**Type**</span></span>|<span data-ttu-id="28d06-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28d06-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="28d06-109">prinID</span><span class="sxs-lookup"><span data-stu-id="28d06-109">prinID</span></span>  <br/> |<span data-ttu-id="28d06-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="28d06-110">int, not null</span></span>  <br/> |<span data-ttu-id="28d06-111">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="28d06-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="28d06-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="28d06-112">memberADPath</span></span>  <br/> |<span data-ttu-id="28d06-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="28d06-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="28d06-p101">Различающееся имя участника. Участник не должен быть субъектом (в таблице tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="28d06-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="28d06-116">**Keys**</span><span class="sxs-lookup"><span data-stu-id="28d06-116">**Keys**</span></span>

|<span data-ttu-id="28d06-117">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="28d06-117">**Column**</span></span>|<span data-ttu-id="28d06-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28d06-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="28d06-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="28d06-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="28d06-120">prinID</span><span class="sxs-lookup"><span data-stu-id="28d06-120">prinID</span></span>  <br/> |<span data-ttu-id="28d06-121">Внешний ключ для поиска в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="28d06-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

