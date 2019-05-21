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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица Сессионкоррелатион является вспомогательной таблицей. Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294658"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="a6407-104">Таблица SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="a6407-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="a6407-105">Таблица Сессионкоррелатион является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="a6407-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="a6407-106">Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="a6407-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="a6407-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a6407-107">**Column**</span></span>|<span data-ttu-id="a6407-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a6407-108">**Data Type**</span></span>|<span data-ttu-id="a6407-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a6407-109">**Key/Index**</span></span>|<span data-ttu-id="a6407-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a6407-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a6407-111">**Счет**</span><span class="sxs-lookup"><span data-stu-id="a6407-111">**Checksum**</span></span> <br/> |<span data-ttu-id="a6407-112">целое</span><span class="sxs-lookup"><span data-stu-id="a6407-112">int</span></span>  <br/> |||
|<span data-ttu-id="a6407-113">**Коррелатионкэй**</span><span class="sxs-lookup"><span data-stu-id="a6407-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="a6407-114">целое</span><span class="sxs-lookup"><span data-stu-id="a6407-114">int</span></span>  <br/> |<span data-ttu-id="a6407-115">Primary</span><span class="sxs-lookup"><span data-stu-id="a6407-115">Primary</span></span>  <br/> |<span data-ttu-id="a6407-116">Уникальный номер, показывающий этот сервер конференц-связи A/V.</span><span class="sxs-lookup"><span data-stu-id="a6407-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="a6407-117">**Корреляци**</span><span class="sxs-lookup"><span data-stu-id="a6407-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="a6407-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a6407-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a6407-119">Повторя</span><span class="sxs-lookup"><span data-stu-id="a6407-119">Unique</span></span>  <br/> |<span data-ttu-id="a6407-120">Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="a6407-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="a6407-121">**Некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="a6407-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="a6407-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a6407-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="a6407-123">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a6407-123">For internal use only.</span></span>  <br/> |
   

