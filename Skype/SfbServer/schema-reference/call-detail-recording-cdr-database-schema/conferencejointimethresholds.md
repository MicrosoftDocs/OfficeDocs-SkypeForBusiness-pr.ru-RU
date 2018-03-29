---
title: Таблица conferencejointimethresholds в Скайп для Business Server 2015
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
ms.openlocfilehash: 3646337c9e9f20ac0b1dabfdd5504ce83dfa5c40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f63d6-104">Таблица conferencejointimethresholds в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f63d6-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f63d6-105">Таблица conferencejointimethresholds содержит границ классификации, используемых отчету о Сводка времени присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="f63d6-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="f63d6-106">В сводном отчете время присоединения к конференции обобщаются количество времени, необходимое для пользователей, для успешного присоединения к конференции; Эти значения времени сообщает и как среднее значение, так и в одной из следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="f63d6-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="f63d6-107">Менее 2 секунд.</span><span class="sxs-lookup"><span data-stu-id="f63d6-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="f63d6-108">От 2 до 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="f63d6-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="f63d6-109">От 5 до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="f63d6-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="f63d6-110">Более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="f63d6-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="f63d6-111">Таблица conferencejointimethresholds содержит значения классификации 2 секунд, 5 секунд и 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="f63d6-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="f63d6-112">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f63d6-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f63d6-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f63d6-113">**Column**</span></span>|<span data-ttu-id="f63d6-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="f63d6-114">**Data Type**</span></span>|<span data-ttu-id="f63d6-115">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="f63d6-115">**Key/Index**</span></span>|<span data-ttu-id="f63d6-116">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="f63d6-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f63d6-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="f63d6-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="f63d6-118">целое</span><span class="sxs-lookup"><span data-stu-id="f63d6-118">int</span></span>  <br/> |<span data-ttu-id="f63d6-119">Primary</span><span class="sxs-lookup"><span data-stu-id="f63d6-119">Primary</span></span>  <br/> |<span data-ttu-id="f63d6-120">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="f63d6-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="f63d6-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="f63d6-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="f63d6-122">целое</span><span class="sxs-lookup"><span data-stu-id="f63d6-122">int</span></span>  <br/> || <span data-ttu-id="f63d6-123">Верхняя граница для классификации.</span><span class="sxs-lookup"><span data-stu-id="f63d6-123">Upper limit for the classification.</span></span> <span data-ttu-id="f63d6-124">Доступны значения:</span><span class="sxs-lookup"><span data-stu-id="f63d6-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="f63d6-125">2</span><span class="sxs-lookup"><span data-stu-id="f63d6-125">2</span></span> <br/>  <span data-ttu-id="f63d6-126">5</span><span class="sxs-lookup"><span data-stu-id="f63d6-126">5</span></span> <br/>  <span data-ttu-id="f63d6-127">10</span><span class="sxs-lookup"><span data-stu-id="f63d6-127">10</span></span> <br/> |
   

