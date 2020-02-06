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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814617"
---
# <a name="tblenumattribute"></a><span data-ttu-id="b8427-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="b8427-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="b8427-104">Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.</span><span class="sxs-lookup"><span data-stu-id="b8427-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="b8427-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="b8427-105">**Columns**</span></span>

|<span data-ttu-id="b8427-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b8427-106">**Column**</span></span>|<span data-ttu-id="b8427-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b8427-107">**Type**</span></span>|<span data-ttu-id="b8427-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b8427-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8427-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="b8427-109">attributeID</span></span>  <br/> |<span data-ttu-id="b8427-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b8427-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b8427-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="b8427-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="b8427-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="b8427-112">attributeName</span></span>  <br/> |<span data-ttu-id="b8427-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b8427-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b8427-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="b8427-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="b8427-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="b8427-115">**Key**</span></span>

|<span data-ttu-id="b8427-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b8427-116">**Column**</span></span>|<span data-ttu-id="b8427-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b8427-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b8427-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="b8427-118">attributeID</span></span>  <br/> |<span data-ttu-id="b8427-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="b8427-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b8427-120">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="b8427-120">**Table Values**</span></span>

|<span data-ttu-id="b8427-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="b8427-121">**attributeID**</span></span>|<span data-ttu-id="b8427-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="b8427-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b8427-123">1</span><span class="sxs-lookup"><span data-stu-id="b8427-123">1</span></span>  <br/> |<span data-ttu-id="b8427-124">Отображение.</span><span class="sxs-lookup"><span data-stu-id="b8427-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="b8427-125">2</span><span class="sxs-lookup"><span data-stu-id="b8427-125">2</span></span>  <br/> |<span data-ttu-id="b8427-126">Расширения.</span><span class="sxs-lookup"><span data-stu-id="b8427-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b8427-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b8427-127">See also</span></span>

[<span data-ttu-id="b8427-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="b8427-128">tblNode</span></span>](tblnode.md)
