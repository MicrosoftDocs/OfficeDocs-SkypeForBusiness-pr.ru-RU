---
title: Таблица codecdescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Таблица codecdescription назначение уникальных идентификаторов кодека соответствующему кодеку. Кодеки используется для кодирования цифровых сигналов для передачи и вещания, а затем для декодирования этих сигналов для воспроизведения. Эта таблица была введена в Microsoft Lync Server 2013
ms.openlocfilehash: efda27afe9312c25add8be0f74364384aed53b3e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896500"
---
# <a name="codecdescription-table"></a><span data-ttu-id="da2bc-105">Таблица codecdescription</span><span class="sxs-lookup"><span data-stu-id="da2bc-105">CodecDescription table</span></span>
 
<span data-ttu-id="da2bc-106">Таблица codecdescription назначение уникальных идентификаторов кодека соответствующему кодеку.</span><span class="sxs-lookup"><span data-stu-id="da2bc-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="da2bc-107">Кодеки используется для кодирования цифровых сигналов для передачи и вещания, а затем для декодирования этих сигналов для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="da2bc-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="da2bc-108">Эта таблица была введена в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da2bc-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="da2bc-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="da2bc-109">**Column**</span></span>|<span data-ttu-id="da2bc-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="da2bc-110">**Data Type**</span></span>|<span data-ttu-id="da2bc-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="da2bc-111">**Key/Index**</span></span>|<span data-ttu-id="da2bc-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="da2bc-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da2bc-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="da2bc-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="da2bc-114">smallint</span><span class="sxs-lookup"><span data-stu-id="da2bc-114">smallint</span></span>  <br/> |<span data-ttu-id="da2bc-115">Primary</span><span class="sxs-lookup"><span data-stu-id="da2bc-115">Primary</span></span>  <br/> |<span data-ttu-id="da2bc-116">Уникальный идентификатор, назначенный кодеку.</span><span class="sxs-lookup"><span data-stu-id="da2bc-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="da2bc-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="da2bc-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="da2bc-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="da2bc-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="da2bc-119">Уникальный</span><span class="sxs-lookup"><span data-stu-id="da2bc-119">Unique</span></span>  <br/> |<span data-ttu-id="da2bc-120">Уникальное описание кодека, соответствующего codecdescriptionkey.</span><span class="sxs-lookup"><span data-stu-id="da2bc-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

