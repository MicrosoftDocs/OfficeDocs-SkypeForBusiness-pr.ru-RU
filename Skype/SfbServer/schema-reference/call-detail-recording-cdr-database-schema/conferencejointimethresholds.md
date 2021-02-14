---
title: Таблица ConferenceJoinTimeThresholds в Skype для бизнеса Server 2015
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813309"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="890f6-104">Таблица ConferenceJoinTimeThresholds в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="890f6-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="890f6-p102">Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="890f6-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="890f6-107">менее 2 секунд;</span><span class="sxs-lookup"><span data-stu-id="890f6-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="890f6-108">от 2 до 5 секунд;</span><span class="sxs-lookup"><span data-stu-id="890f6-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="890f6-109">от 5 до 10 секунд;</span><span class="sxs-lookup"><span data-stu-id="890f6-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="890f6-110">более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="890f6-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="890f6-111">Таблица ConferenceJoinTimeThresholds содержит значения классификации для 2 секунд, 5 секунд и 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="890f6-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="890f6-112">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="890f6-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="890f6-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="890f6-113">**Column**</span></span>|<span data-ttu-id="890f6-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="890f6-114">**Data Type**</span></span>|<span data-ttu-id="890f6-115">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="890f6-115">**Key/Index**</span></span>|<span data-ttu-id="890f6-116">**Details**</span><span class="sxs-lookup"><span data-stu-id="890f6-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="890f6-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="890f6-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="890f6-118">int</span><span class="sxs-lookup"><span data-stu-id="890f6-118">int</span></span>  <br/> |<span data-ttu-id="890f6-119">Primary</span><span class="sxs-lookup"><span data-stu-id="890f6-119">Primary</span></span>  <br/> |<span data-ttu-id="890f6-120">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="890f6-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="890f6-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="890f6-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="890f6-122">int</span><span class="sxs-lookup"><span data-stu-id="890f6-122">int</span></span>  <br/> || <span data-ttu-id="890f6-p103">Верхняя граница для классификации. Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="890f6-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="890f6-125">2 </span><span class="sxs-lookup"><span data-stu-id="890f6-125">2</span></span> <br/>  <span data-ttu-id="890f6-126">5 </span><span class="sxs-lookup"><span data-stu-id="890f6-126">5</span></span> <br/>  <span data-ttu-id="890f6-127">10 </span><span class="sxs-lookup"><span data-stu-id="890f6-127">10</span></span> <br/> |
   

