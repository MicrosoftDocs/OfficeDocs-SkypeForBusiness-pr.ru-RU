---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations содержит связи, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831429"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="2c36a-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="2c36a-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="2c36a-104">tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).</span><span class="sxs-lookup"><span data-stu-id="2c36a-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="2c36a-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="2c36a-105">**Columns**</span></span>

|<span data-ttu-id="2c36a-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2c36a-106">**Column**</span></span>|<span data-ttu-id="2c36a-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2c36a-107">**Type**</span></span>|<span data-ttu-id="2c36a-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2c36a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c36a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="2c36a-109">prinID</span></span>  <br/> |<span data-ttu-id="2c36a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="2c36a-110">int, not null</span></span>  <br/> |<span data-ttu-id="2c36a-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="2c36a-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="2c36a-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="2c36a-112">affDescription</span></span>  <br/> |<span data-ttu-id="2c36a-113">nvarchar (256), не NULL</span><span class="sxs-lookup"><span data-stu-id="2c36a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2c36a-114">Строка, идентифицирующая принадлежность.</span><span class="sxs-lookup"><span data-stu-id="2c36a-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="2c36a-115">Формат: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span><span class="sxs-lookup"><span data-stu-id="2c36a-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="2c36a-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="2c36a-116">updatedBy</span></span>  <br/> |<span data-ttu-id="2c36a-117">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="2c36a-117">int, not null</span></span>  <br/> |<span data-ttu-id="2c36a-p101">Идентификатор субъекта, обновившего эту строку. Он всегда равен 1 (системный пользователь) поскольку синхронизация Active Directory является единственным источником этих записей.</span><span class="sxs-lookup"><span data-stu-id="2c36a-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="2c36a-120">**Keys**</span><span class="sxs-lookup"><span data-stu-id="2c36a-120">**Keys**</span></span>

|<span data-ttu-id="2c36a-121">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="2c36a-121">**Column(s)**</span></span>|<span data-ttu-id="2c36a-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2c36a-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="2c36a-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="2c36a-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2c36a-124">prinID</span><span class="sxs-lookup"><span data-stu-id="2c36a-124">prinID</span></span>  <br/> |<span data-ttu-id="2c36a-125">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="2c36a-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

