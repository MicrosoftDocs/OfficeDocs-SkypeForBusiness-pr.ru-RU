---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations содержит принадлежности, которые не удалось прочитать (обычно вследствие ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212609"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="8a49b-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="8a49b-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="8a49b-104">tblSkippedAffiliations содержит принадлежности, которые не удалось прочитать (обычно вследствие ошибок доступа к доменным службам Active Directory).</span><span class="sxs-lookup"><span data-stu-id="8a49b-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="8a49b-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="8a49b-105">**Columns**</span></span>

|<span data-ttu-id="8a49b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8a49b-106">**Column**</span></span>|<span data-ttu-id="8a49b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8a49b-107">**Type**</span></span>|<span data-ttu-id="8a49b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8a49b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8a49b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="8a49b-109">prinID</span></span>  <br/> |<span data-ttu-id="8a49b-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="8a49b-110">int, not null</span></span>  <br/> |<span data-ttu-id="8a49b-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="8a49b-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8a49b-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="8a49b-112">affDescription</span></span>  <br/> |<span data-ttu-id="8a49b-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="8a49b-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="8a49b-114">Строка, идентифицирующая принадлежность.</span><span class="sxs-lookup"><span data-stu-id="8a49b-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="8a49b-115">Имеет формат: guid: _{0}_ uri: _{1}_> id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="8a49b-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="8a49b-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="8a49b-116">updatedBy</span></span>  <br/> |<span data-ttu-id="8a49b-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="8a49b-117">int, not null</span></span>  <br/> |<span data-ttu-id="8a49b-118">Идентификатор субъекта, который обновления этой строки.</span><span class="sxs-lookup"><span data-stu-id="8a49b-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="8a49b-119">Это всегда 1 (система пользователя), так как синхронизации Active Directory является единственным источником для этих операций.</span><span class="sxs-lookup"><span data-stu-id="8a49b-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="8a49b-120">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="8a49b-120">**Keys**</span></span>

|<span data-ttu-id="8a49b-121">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="8a49b-121">**Column(s)**</span></span>|<span data-ttu-id="8a49b-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8a49b-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a49b-123">\<prinID affDescription\></span><span class="sxs-lookup"><span data-stu-id="8a49b-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="8a49b-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8a49b-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8a49b-125">prinID</span><span class="sxs-lookup"><span data-stu-id="8a49b-125">prinID</span></span>  <br/> |<span data-ttu-id="8a49b-126">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="8a49b-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

