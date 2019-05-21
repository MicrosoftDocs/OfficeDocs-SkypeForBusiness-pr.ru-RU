---
title: Таблица Кодекдескриптион
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: В таблице Кодекдескриптион уникальные идентификаторы кодека сопоставляются с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем для расшифровки этих сигналов для воспроизведения. Эта таблица введена в Microsoft Lync Server 2013
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295043"
---
# <a name="codecdescription-table"></a><span data-ttu-id="172fc-105">Таблица Кодекдескриптион</span><span class="sxs-lookup"><span data-stu-id="172fc-105">CodecDescription table</span></span>
 
<span data-ttu-id="172fc-106">В таблице Кодекдескриптион уникальные идентификаторы кодека сопоставляются с соответствующими кодеками.</span><span class="sxs-lookup"><span data-stu-id="172fc-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="172fc-107">Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем для расшифровки этих сигналов для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="172fc-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="172fc-108">Эта таблица введена в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="172fc-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="172fc-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="172fc-109">**Column**</span></span>|<span data-ttu-id="172fc-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="172fc-110">**Data Type**</span></span>|<span data-ttu-id="172fc-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="172fc-111">**Key/Index**</span></span>|<span data-ttu-id="172fc-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="172fc-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="172fc-113">**Кодекдескриптионкэй**</span><span class="sxs-lookup"><span data-stu-id="172fc-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="172fc-114">smallint</span><span class="sxs-lookup"><span data-stu-id="172fc-114">smallint</span></span>  <br/> |<span data-ttu-id="172fc-115">Primary</span><span class="sxs-lookup"><span data-stu-id="172fc-115">Primary</span></span>  <br/> |<span data-ttu-id="172fc-116">Уникальный идентификатор, присвоенный кодеку.</span><span class="sxs-lookup"><span data-stu-id="172fc-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="172fc-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="172fc-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="172fc-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="172fc-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="172fc-119">Повторя</span><span class="sxs-lookup"><span data-stu-id="172fc-119">Unique</span></span>  <br/> |<span data-ttu-id="172fc-120">Уникальное описание кодека, соответствующего Кодекдескриптионкэй.</span><span class="sxs-lookup"><span data-stu-id="172fc-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

