---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute — это таблица содержит атрибуты Visibility и Behavior, используемые в таблице Node.
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a><span data-ttu-id="4ea15-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="4ea15-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="4ea15-104">tblEnumAttribute — это таблица содержит атрибуты Visibility и Behavior, используемые в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="4ea15-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="4ea15-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="4ea15-105">**Columns**</span></span>

|<span data-ttu-id="4ea15-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4ea15-106">**Column**</span></span>|<span data-ttu-id="4ea15-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4ea15-107">**Type**</span></span>|<span data-ttu-id="4ea15-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4ea15-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ea15-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="4ea15-109">attributeID</span></span>  <br/> |<span data-ttu-id="4ea15-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="4ea15-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="4ea15-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="4ea15-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="4ea15-112">Имя_атрибута</span><span class="sxs-lookup"><span data-stu-id="4ea15-112">attributeName</span></span>  <br/> |<span data-ttu-id="4ea15-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="4ea15-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="4ea15-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="4ea15-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="4ea15-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="4ea15-115">**Key**</span></span>

|<span data-ttu-id="4ea15-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4ea15-116">**Column**</span></span>|<span data-ttu-id="4ea15-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4ea15-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ea15-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="4ea15-118">attributeID</span></span>  <br/> |<span data-ttu-id="4ea15-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="4ea15-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="4ea15-120">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="4ea15-120">**Table Values**</span></span>

|<span data-ttu-id="4ea15-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="4ea15-121">**attributeID**</span></span>|<span data-ttu-id="4ea15-122">**Имя_атрибута**</span><span class="sxs-lookup"><span data-stu-id="4ea15-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ea15-123">1</span><span class="sxs-lookup"><span data-stu-id="4ea15-123">1</span></span>  <br/> |<span data-ttu-id="4ea15-124">Видимость.</span><span class="sxs-lookup"><span data-stu-id="4ea15-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="4ea15-125">2</span><span class="sxs-lookup"><span data-stu-id="4ea15-125">2</span></span>  <br/> |<span data-ttu-id="4ea15-126">Поведение.</span><span class="sxs-lookup"><span data-stu-id="4ea15-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4ea15-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4ea15-127">See also</span></span>

#### 

[<span data-ttu-id="4ea15-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="4ea15-128">tblNode</span></span>](tblnode.md)

