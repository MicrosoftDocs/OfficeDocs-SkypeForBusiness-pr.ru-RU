---
title: Таблица SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица Сессионкоррелатион является вспомогательной таблицей. Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805747"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="06554-104">Таблица SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="06554-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="06554-105">Таблица Сессионкоррелатион является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="06554-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="06554-106">Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="06554-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="06554-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="06554-107">**Column**</span></span>|<span data-ttu-id="06554-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06554-108">**Data Type**</span></span>|<span data-ttu-id="06554-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="06554-109">**Key/Index**</span></span>|<span data-ttu-id="06554-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="06554-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="06554-111">**Счет**</span><span class="sxs-lookup"><span data-stu-id="06554-111">**Checksum**</span></span> <br/> |<span data-ttu-id="06554-112">целое</span><span class="sxs-lookup"><span data-stu-id="06554-112">int</span></span>  <br/> |||
|<span data-ttu-id="06554-113">**коррелатионкэй**</span><span class="sxs-lookup"><span data-stu-id="06554-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="06554-114">целое</span><span class="sxs-lookup"><span data-stu-id="06554-114">int</span></span>  <br/> |<span data-ttu-id="06554-115">Primary</span><span class="sxs-lookup"><span data-stu-id="06554-115">Primary</span></span>  <br/> |<span data-ttu-id="06554-116">Уникальный номер, показывающий этот сервер конференц-связи A/V.</span><span class="sxs-lookup"><span data-stu-id="06554-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="06554-117">**Корреляци**</span><span class="sxs-lookup"><span data-stu-id="06554-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="06554-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06554-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="06554-119">Повторя</span><span class="sxs-lookup"><span data-stu-id="06554-119">Unique</span></span>  <br/> |<span data-ttu-id="06554-120">Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="06554-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="06554-121">**некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="06554-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="06554-122">datetime</span><span class="sxs-lookup"><span data-stu-id="06554-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="06554-123">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="06554-123">For internal use only.</span></span>  <br/> |
   

