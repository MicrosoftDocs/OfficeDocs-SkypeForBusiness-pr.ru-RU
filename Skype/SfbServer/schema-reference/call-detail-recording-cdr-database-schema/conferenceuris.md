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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213216"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5a988-104">Таблица ConferenceUris в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a988-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5a988-105">В таблице ConfereneUris представляет собой вспомогательную таблицу, в которой хранится список различных конференции URI, которые участвовали в сеансах конференц записаны в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5a988-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="5a988-106">Каждая запись в таблице представляет одну URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5a988-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="5a988-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5a988-107">**Column**</span></span>|<span data-ttu-id="5a988-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5a988-108">**Data Type**</span></span>|<span data-ttu-id="5a988-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="5a988-109">**Key/Index**</span></span>|<span data-ttu-id="5a988-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="5a988-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5a988-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5a988-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5a988-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5a988-112">datetime</span></span>  <br/> |<span data-ttu-id="5a988-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5a988-113">Primary</span></span>  <br/> |<span data-ttu-id="5a988-114">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="5a988-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="5a988-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="5a988-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="5a988-116">целое</span><span class="sxs-lookup"><span data-stu-id="5a988-116">int</span></span>  <br/> |<span data-ttu-id="5a988-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5a988-117">Primary</span></span>  <br/> |<span data-ttu-id="5a988-118">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5a988-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="5a988-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="5a988-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="5a988-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="5a988-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="5a988-121">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5a988-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="5a988-122">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="5a988-122">**Checksum**</span></span> <br/> |<span data-ttu-id="5a988-123">целое</span><span class="sxs-lookup"><span data-stu-id="5a988-123">int</span></span>  <br/> ||<span data-ttu-id="5a988-124">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5a988-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="5a988-125">Используется для ускоряет базы данных поиска.</span><span class="sxs-lookup"><span data-stu-id="5a988-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="5a988-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="5a988-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="5a988-127">целое</span><span class="sxs-lookup"><span data-stu-id="5a988-127">int</span></span>  <br/> |<span data-ttu-id="5a988-128">Внешний</span><span class="sxs-lookup"><span data-stu-id="5a988-128">Foreign</span></span>  <br/> |<span data-ttu-id="5a988-129">Тип URI, например conf:chat для обмена Мгновенными сообщениями или conf:audio-видео для аудиовизуальной конференции.</span><span class="sxs-lookup"><span data-stu-id="5a988-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="5a988-130">В таблице [UriTypes таблицы](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="5a988-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

