---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295421"
---
# <a name="tblenumattribute"></a><span data-ttu-id="003f6-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="003f6-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="003f6-104">Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.</span><span class="sxs-lookup"><span data-stu-id="003f6-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="003f6-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="003f6-105">**Columns**</span></span>

|<span data-ttu-id="003f6-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="003f6-106">**Column**</span></span>|<span data-ttu-id="003f6-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="003f6-107">**Type**</span></span>|<span data-ttu-id="003f6-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="003f6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="003f6-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="003f6-109">attributeID</span></span>  <br/> |<span data-ttu-id="003f6-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="003f6-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="003f6-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="003f6-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="003f6-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="003f6-112">attributeName</span></span>  <br/> |<span data-ttu-id="003f6-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="003f6-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="003f6-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="003f6-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="003f6-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="003f6-115">**Key**</span></span>

|<span data-ttu-id="003f6-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="003f6-116">**Column**</span></span>|<span data-ttu-id="003f6-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="003f6-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="003f6-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="003f6-118">attributeID</span></span>  <br/> |<span data-ttu-id="003f6-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="003f6-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="003f6-120">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="003f6-120">**Table Values**</span></span>

|<span data-ttu-id="003f6-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="003f6-121">**attributeID**</span></span>|<span data-ttu-id="003f6-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="003f6-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="003f6-123">1</span><span class="sxs-lookup"><span data-stu-id="003f6-123">1</span></span>  <br/> |<span data-ttu-id="003f6-124">Отображение.</span><span class="sxs-lookup"><span data-stu-id="003f6-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="003f6-125">2</span><span class="sxs-lookup"><span data-stu-id="003f6-125">2</span></span>  <br/> |<span data-ttu-id="003f6-126">Расширения.</span><span class="sxs-lookup"><span data-stu-id="003f6-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="003f6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="003f6-127">See also</span></span>

[<span data-ttu-id="003f6-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="003f6-128">tblNode</span></span>](tblnode.md)
