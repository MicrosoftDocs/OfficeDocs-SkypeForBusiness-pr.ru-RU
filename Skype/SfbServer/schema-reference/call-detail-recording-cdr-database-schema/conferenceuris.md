---
title: Таблица ConferenceUris в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: В таблице ConfereneUris представляет собой вспомогательную таблицу, в которой хранится список различных конференции URI, которые участвовали в сеансах конференц записаны в базе данных. Каждая запись в таблице представляет одну URI конференции.
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887773"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4ffde-104">Таблица ConferenceUris в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4ffde-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4ffde-105">В таблице ConfereneUris представляет собой вспомогательную таблицу, в которой хранится список различных конференции URI, которые участвовали в сеансах конференц записаны в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4ffde-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="4ffde-106">Каждая запись в таблице представляет одну URI конференции.</span><span class="sxs-lookup"><span data-stu-id="4ffde-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="4ffde-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4ffde-107">**Column**</span></span>|<span data-ttu-id="4ffde-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4ffde-108">**Data Type**</span></span>|<span data-ttu-id="4ffde-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4ffde-109">**Key/Index**</span></span>|<span data-ttu-id="4ffde-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4ffde-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ffde-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4ffde-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4ffde-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4ffde-112">datetime</span></span>  <br/> |<span data-ttu-id="4ffde-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4ffde-113">Primary</span></span>  <br/> |<span data-ttu-id="4ffde-114">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="4ffde-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="4ffde-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="4ffde-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="4ffde-116">целое</span><span class="sxs-lookup"><span data-stu-id="4ffde-116">int</span></span>  <br/> |<span data-ttu-id="4ffde-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4ffde-117">Primary</span></span>  <br/> |<span data-ttu-id="4ffde-118">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="4ffde-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="4ffde-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="4ffde-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="4ffde-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4ffde-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="4ffde-121">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="4ffde-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="4ffde-122">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="4ffde-122">**Checksum**</span></span> <br/> |<span data-ttu-id="4ffde-123">целое</span><span class="sxs-lookup"><span data-stu-id="4ffde-123">int</span></span>  <br/> ||<span data-ttu-id="4ffde-124">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="4ffde-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="4ffde-125">Используется для ускоряет базы данных поиска.</span><span class="sxs-lookup"><span data-stu-id="4ffde-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="4ffde-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="4ffde-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="4ffde-127">целое</span><span class="sxs-lookup"><span data-stu-id="4ffde-127">int</span></span>  <br/> |<span data-ttu-id="4ffde-128">Внешний</span><span class="sxs-lookup"><span data-stu-id="4ffde-128">Foreign</span></span>  <br/> |<span data-ttu-id="4ffde-129">Тип URI, например conf:chat для обмена Мгновенными сообщениями или conf:audio-видео для аудиовизуальной конференции.</span><span class="sxs-lookup"><span data-stu-id="4ffde-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="4ffde-130">В таблице [UriTypes таблицы](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="4ffde-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

