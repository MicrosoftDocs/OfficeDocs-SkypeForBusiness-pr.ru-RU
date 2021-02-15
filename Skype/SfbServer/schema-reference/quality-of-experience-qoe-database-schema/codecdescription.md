---
title: Таблица CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица была представлена в Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831349"
---
# <a name="codecdescription-table"></a><span data-ttu-id="2a1a5-105">Таблица CodecDescription</span><span class="sxs-lookup"><span data-stu-id="2a1a5-105">CodecDescription table</span></span>
 
<span data-ttu-id="2a1a5-106">В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="2a1a5-107">Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="2a1a5-108">Эта таблица была представлена в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a1a5-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="2a1a5-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a1a5-109">**Column**</span></span>|<span data-ttu-id="2a1a5-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2a1a5-110">**Data Type**</span></span>|<span data-ttu-id="2a1a5-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="2a1a5-111">**Key/Index**</span></span>|<span data-ttu-id="2a1a5-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="2a1a5-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a1a5-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="2a1a5-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="2a1a5-114">smallint</span><span class="sxs-lookup"><span data-stu-id="2a1a5-114">smallint</span></span>  <br/> |<span data-ttu-id="2a1a5-115">Primary</span><span class="sxs-lookup"><span data-stu-id="2a1a5-115">Primary</span></span>  <br/> |<span data-ttu-id="2a1a5-116">Уникальный идентификатор, назначенный кодеку.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="2a1a5-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="2a1a5-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="2a1a5-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a1a5-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="2a1a5-119">Уникальные</span><span class="sxs-lookup"><span data-stu-id="2a1a5-119">Unique</span></span>  <br/> |<span data-ttu-id="2a1a5-120">Уникальное описание кодека, соответствующего CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

