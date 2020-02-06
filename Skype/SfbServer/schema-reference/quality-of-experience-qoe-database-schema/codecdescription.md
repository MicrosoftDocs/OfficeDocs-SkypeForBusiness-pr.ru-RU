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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: В таблице Кодекдескриптион уникальные идентификаторы кодека сопоставляются с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем для расшифровки этих сигналов для воспроизведения. Эта таблица введена в Microsoft Lync Server 2013
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810367"
---
# <a name="codecdescription-table"></a><span data-ttu-id="c764f-105">Таблица Кодекдескриптион</span><span class="sxs-lookup"><span data-stu-id="c764f-105">CodecDescription table</span></span>
 
<span data-ttu-id="c764f-106">В таблице Кодекдескриптион уникальные идентификаторы кодека сопоставляются с соответствующими кодеками.</span><span class="sxs-lookup"><span data-stu-id="c764f-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="c764f-107">Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем для расшифровки этих сигналов для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="c764f-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="c764f-108">Эта таблица введена в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c764f-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="c764f-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c764f-109">**Column**</span></span>|<span data-ttu-id="c764f-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c764f-110">**Data Type**</span></span>|<span data-ttu-id="c764f-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="c764f-111">**Key/Index**</span></span>|<span data-ttu-id="c764f-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c764f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c764f-113">**кодекдескриптионкэй**</span><span class="sxs-lookup"><span data-stu-id="c764f-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="c764f-114">smallint</span><span class="sxs-lookup"><span data-stu-id="c764f-114">smallint</span></span>  <br/> |<span data-ttu-id="c764f-115">Primary</span><span class="sxs-lookup"><span data-stu-id="c764f-115">Primary</span></span>  <br/> |<span data-ttu-id="c764f-116">Уникальный идентификатор, присвоенный кодеку.</span><span class="sxs-lookup"><span data-stu-id="c764f-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="c764f-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="c764f-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="c764f-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c764f-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="c764f-119">Повторя</span><span class="sxs-lookup"><span data-stu-id="c764f-119">Unique</span></span>  <br/> |<span data-ttu-id="c764f-120">Уникальное описание кодека, соответствующего Кодекдескриптионкэй.</span><span class="sxs-lookup"><span data-stu-id="c764f-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

