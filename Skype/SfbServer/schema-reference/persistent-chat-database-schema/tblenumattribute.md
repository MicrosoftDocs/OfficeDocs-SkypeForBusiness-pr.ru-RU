---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute — это таблица содержит атрибуты Visibility и Behavior, используемые в таблице Node.
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929954"
---
# <a name="tblenumattribute"></a><span data-ttu-id="8a533-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="8a533-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="8a533-104">tblEnumAttribute — это таблица содержит атрибуты Visibility и Behavior, используемые в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="8a533-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="8a533-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="8a533-105">**Columns**</span></span>

|<span data-ttu-id="8a533-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8a533-106">**Column**</span></span>|<span data-ttu-id="8a533-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8a533-107">**Type**</span></span>|<span data-ttu-id="8a533-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8a533-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8a533-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="8a533-109">attributeID</span></span>  <br/> |<span data-ttu-id="8a533-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="8a533-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="8a533-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="8a533-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="8a533-112">Имя_атрибута</span><span class="sxs-lookup"><span data-stu-id="8a533-112">attributeName</span></span>  <br/> |<span data-ttu-id="8a533-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="8a533-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="8a533-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="8a533-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="8a533-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="8a533-115">**Key**</span></span>

|<span data-ttu-id="8a533-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8a533-116">**Column**</span></span>|<span data-ttu-id="8a533-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8a533-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a533-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="8a533-118">attributeID</span></span>  <br/> |<span data-ttu-id="8a533-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8a533-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="8a533-120">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="8a533-120">**Table Values**</span></span>

|<span data-ttu-id="8a533-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="8a533-121">**attributeID**</span></span>|<span data-ttu-id="8a533-122">**Имя_атрибута**</span><span class="sxs-lookup"><span data-stu-id="8a533-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a533-123">1</span><span class="sxs-lookup"><span data-stu-id="8a533-123">1</span></span>  <br/> |<span data-ttu-id="8a533-124">Видимость.</span><span class="sxs-lookup"><span data-stu-id="8a533-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="8a533-125">2</span><span class="sxs-lookup"><span data-stu-id="8a533-125">2</span></span>  <br/> |<span data-ttu-id="8a533-126">Поведение.</span><span class="sxs-lookup"><span data-stu-id="8a533-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8a533-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8a533-127">See also</span></span>

[<span data-ttu-id="8a533-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="8a533-128">tblNode</span></span>](tblnode.md)
