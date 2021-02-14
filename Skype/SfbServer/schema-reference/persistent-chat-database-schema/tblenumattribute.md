---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: Жестко запрограммированная таблица tblEnumAttribute содержит атрибуты Visibility и Behavior, которые используются в таблице Node.
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809719"
---
# <a name="tblenumattribute"></a><span data-ttu-id="c2b8b-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="c2b8b-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="c2b8b-104">Жестко запрограммированная таблица tblEnumAttribute содержит атрибуты Visibility и Behavior, которые используются в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="c2b8b-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="c2b8b-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-105">**Columns**</span></span>

|<span data-ttu-id="c2b8b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-106">**Column**</span></span>|<span data-ttu-id="c2b8b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-107">**Type**</span></span>|<span data-ttu-id="c2b8b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2b8b-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="c2b8b-109">attributeID</span></span>  <br/> |<span data-ttu-id="c2b8b-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="c2b8b-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="c2b8b-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="c2b8b-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="c2b8b-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="c2b8b-112">attributeName</span></span>  <br/> |<span data-ttu-id="c2b8b-113">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="c2b8b-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c2b8b-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="c2b8b-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="c2b8b-115">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-115">**Key**</span></span>

|<span data-ttu-id="c2b8b-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-116">**Column**</span></span>|<span data-ttu-id="c2b8b-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c2b8b-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="c2b8b-118">attributeID</span></span>  <br/> |<span data-ttu-id="c2b8b-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c2b8b-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="c2b8b-120">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-120">**Table Values**</span></span>

|<span data-ttu-id="c2b8b-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-121">**attributeID**</span></span>|<span data-ttu-id="c2b8b-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="c2b8b-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c2b8b-123">1 </span><span class="sxs-lookup"><span data-stu-id="c2b8b-123">1</span></span>  <br/> |<span data-ttu-id="c2b8b-124">Видимость.</span><span class="sxs-lookup"><span data-stu-id="c2b8b-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="c2b8b-125">2 </span><span class="sxs-lookup"><span data-stu-id="c2b8b-125">2</span></span>  <br/> |<span data-ttu-id="c2b8b-126">Поведение.</span><span class="sxs-lookup"><span data-stu-id="c2b8b-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c2b8b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c2b8b-127">See also</span></span>

[<span data-ttu-id="c2b8b-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="c2b8b-128">tblNode</span></span>](tblnode.md)
