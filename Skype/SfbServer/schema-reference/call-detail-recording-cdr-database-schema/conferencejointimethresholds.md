---
title: Таблица conferencejointimethresholds в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Таблица conferencejointimethresholds содержит границ классификации, используемых отчету о Сводка времени присоединения к конференции. В сводном отчете время присоединения к конференции обобщаются количество времени, необходимое для пользователей, для успешного присоединения к конференции; Эти значения времени сообщает и как среднее значение, так и в одной из следующих категорий:'
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895819"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="27303-104">Таблица conferencejointimethresholds в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="27303-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="27303-105">Таблица conferencejointimethresholds содержит границ классификации, используемых отчету о Сводка времени присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="27303-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="27303-106">В сводном отчете время присоединения к конференции обобщаются количество времени, необходимое для пользователей, для успешного присоединения к конференции; Эти значения времени сообщает и как среднее значение, так и в одной из следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="27303-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="27303-107">Менее 2 секунд.</span><span class="sxs-lookup"><span data-stu-id="27303-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="27303-108">От 2 до 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="27303-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="27303-109">От 5 до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="27303-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="27303-110">Более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="27303-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="27303-111">Таблица conferencejointimethresholds содержит значения классификации 2 секунд, 5 секунд и 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="27303-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="27303-112">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27303-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="27303-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="27303-113">**Column**</span></span>|<span data-ttu-id="27303-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="27303-114">**Data Type**</span></span>|<span data-ttu-id="27303-115">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="27303-115">**Key/Index**</span></span>|<span data-ttu-id="27303-116">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="27303-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27303-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="27303-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="27303-118">целое</span><span class="sxs-lookup"><span data-stu-id="27303-118">int</span></span>  <br/> |<span data-ttu-id="27303-119">Primary</span><span class="sxs-lookup"><span data-stu-id="27303-119">Primary</span></span>  <br/> |<span data-ttu-id="27303-120">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="27303-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="27303-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="27303-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="27303-122">целое</span><span class="sxs-lookup"><span data-stu-id="27303-122">int</span></span>  <br/> || <span data-ttu-id="27303-123">Верхняя граница для классификации.</span><span class="sxs-lookup"><span data-stu-id="27303-123">Upper limit for the classification.</span></span> <span data-ttu-id="27303-124">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="27303-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="27303-125">2</span><span class="sxs-lookup"><span data-stu-id="27303-125">2</span></span> <br/>  <span data-ttu-id="27303-126">5</span><span class="sxs-lookup"><span data-stu-id="27303-126">5</span></span> <br/>  <span data-ttu-id="27303-127">10</span><span class="sxs-lookup"><span data-stu-id="27303-127">10</span></span> <br/> |
   

