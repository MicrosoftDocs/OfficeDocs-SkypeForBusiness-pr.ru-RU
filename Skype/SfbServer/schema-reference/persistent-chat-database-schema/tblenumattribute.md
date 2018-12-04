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
ms.openlocfilehash: bd386bc77d15c627597a5680277235a05d0c8039
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504868"
---
# <a name="tblenumattribute"></a><span data-ttu-id="abb8e-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="abb8e-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="abb8e-104">tblEnumAttribute — это таблица содержит атрибуты Visibility и Behavior, используемые в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="abb8e-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="abb8e-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="abb8e-105">**Columns**</span></span>

|<span data-ttu-id="abb8e-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="abb8e-106">**Column**</span></span>|<span data-ttu-id="abb8e-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="abb8e-107">**Type**</span></span>|<span data-ttu-id="abb8e-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="abb8e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="abb8e-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="abb8e-109">attributeID</span></span>  <br/> |<span data-ttu-id="abb8e-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="abb8e-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="abb8e-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="abb8e-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="abb8e-112">Имя_атрибута</span><span class="sxs-lookup"><span data-stu-id="abb8e-112">attributeName</span></span>  <br/> |<span data-ttu-id="abb8e-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="abb8e-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="abb8e-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="abb8e-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="abb8e-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="abb8e-115">**Key**</span></span>

|<span data-ttu-id="abb8e-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="abb8e-116">**Column**</span></span>|<span data-ttu-id="abb8e-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="abb8e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="abb8e-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="abb8e-118">attributeID</span></span>  <br/> |<span data-ttu-id="abb8e-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="abb8e-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="abb8e-120">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="abb8e-120">**Table Values**</span></span>

|<span data-ttu-id="abb8e-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="abb8e-121">**attributeID**</span></span>|<span data-ttu-id="abb8e-122">**Имя_атрибута**</span><span class="sxs-lookup"><span data-stu-id="abb8e-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="abb8e-123">1</span><span class="sxs-lookup"><span data-stu-id="abb8e-123">1</span></span>  <br/> |<span data-ttu-id="abb8e-124">Видимость.</span><span class="sxs-lookup"><span data-stu-id="abb8e-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="abb8e-125">2</span><span class="sxs-lookup"><span data-stu-id="abb8e-125">2</span></span>  <br/> |<span data-ttu-id="abb8e-126">Поведение.</span><span class="sxs-lookup"><span data-stu-id="abb8e-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="abb8e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="abb8e-127">See also</span></span>

[<span data-ttu-id="abb8e-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="abb8e-128">tblNode</span></span>](tblnode.md)