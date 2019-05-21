---
title: Таблица Конференцежоинтимесрешолдс в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'В таблице Конференцежоинтимесрешолдс содержатся ограничители классификации, используемые в сводном отчете "время присоединения к Конференции". Сводный отчет о времени присоединения к Конференции суммирует количество времени, необходимого для успешного присоединения пользователей к Конференции; Эти значения времени выводятся как среднее значение и в одной из следующих категорий:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296499"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6520d-104">Таблица Конференцежоинтимесрешолдс в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="6520d-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6520d-105">В таблице Конференцежоинтимесрешолдс содержатся ограничители классификации, используемые в сводном отчете "время присоединения к Конференции".</span><span class="sxs-lookup"><span data-stu-id="6520d-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="6520d-106">Сводный отчет о времени присоединения к Конференции суммирует количество времени, необходимого для успешного присоединения пользователей к Конференции; Эти значения времени выводятся как среднее значение и в одной из следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="6520d-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="6520d-107">Менее 2 секунд.</span><span class="sxs-lookup"><span data-stu-id="6520d-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="6520d-108">От 2 секунды до 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="6520d-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="6520d-109">От 5 секунд до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="6520d-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="6520d-110">Более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="6520d-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="6520d-111">В таблице Конференцежоинтимесрешолдс содержатся значения классификации 2 секунды, 5 секунд и 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="6520d-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="6520d-112">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6520d-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6520d-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6520d-113">**Column**</span></span>|<span data-ttu-id="6520d-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6520d-114">**Data Type**</span></span>|<span data-ttu-id="6520d-115">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="6520d-115">**Key/Index**</span></span>|<span data-ttu-id="6520d-116">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6520d-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6520d-117">**Срешолдид**</span><span class="sxs-lookup"><span data-stu-id="6520d-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="6520d-118">целое</span><span class="sxs-lookup"><span data-stu-id="6520d-118">int</span></span>  <br/> |<span data-ttu-id="6520d-119">Primary</span><span class="sxs-lookup"><span data-stu-id="6520d-119">Primary</span></span>  <br/> |<span data-ttu-id="6520d-120">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="6520d-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="6520d-121">**Срешолдвалуе**</span><span class="sxs-lookup"><span data-stu-id="6520d-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="6520d-122">целое</span><span class="sxs-lookup"><span data-stu-id="6520d-122">int</span></span>  <br/> || <span data-ttu-id="6520d-123">Верхний предел для классификации.</span><span class="sxs-lookup"><span data-stu-id="6520d-123">Upper limit for the classification.</span></span> <span data-ttu-id="6520d-124">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="6520d-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="6520d-125">2</span><span class="sxs-lookup"><span data-stu-id="6520d-125">2</span></span> <br/>  <span data-ttu-id="6520d-126">5</span><span class="sxs-lookup"><span data-stu-id="6520d-126">5</span></span> <br/>  <span data-ttu-id="6520d-127">5-10</span><span class="sxs-lookup"><span data-stu-id="6520d-127">10</span></span> <br/> |
   

