---
title: Таблица Конференцеурис в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Таблица Конференеурис является вспомогательной таблицей, в которой хранится список различных URI конференций, участвующих в сеансах конференц-связи, записанных в базу данных. Каждая запись в таблице представляет один URI конференции.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815317"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a0189-104">Таблица Конференцеурис в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a0189-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a0189-105">Таблица Конференеурис является вспомогательной таблицей, в которой хранится список различных URI конференций, участвующих в сеансах конференц-связи, записанных в базу данных.</span><span class="sxs-lookup"><span data-stu-id="a0189-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="a0189-106">Каждая запись в таблице представляет один URI конференции.</span><span class="sxs-lookup"><span data-stu-id="a0189-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="a0189-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a0189-107">**Column**</span></span>|<span data-ttu-id="a0189-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a0189-108">**Data Type**</span></span>|<span data-ttu-id="a0189-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a0189-109">**Key/Index**</span></span>|<span data-ttu-id="a0189-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a0189-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a0189-111">**некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="a0189-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="a0189-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a0189-112">datetime</span></span>  <br/> |<span data-ttu-id="a0189-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a0189-113">Primary</span></span>  <br/> |<span data-ttu-id="a0189-114">Метка времени, используемая в качестве внутренней.</span><span class="sxs-lookup"><span data-stu-id="a0189-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="a0189-115">**конференцеуриид**</span><span class="sxs-lookup"><span data-stu-id="a0189-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="a0189-116">целое</span><span class="sxs-lookup"><span data-stu-id="a0189-116">int</span></span>  <br/> |<span data-ttu-id="a0189-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a0189-117">Primary</span></span>  <br/> |<span data-ttu-id="a0189-118">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="a0189-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="a0189-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="a0189-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="a0189-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a0189-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="a0189-121">Универсальный код ресурса (URI) Конференции.</span><span class="sxs-lookup"><span data-stu-id="a0189-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="a0189-122">**Счет**</span><span class="sxs-lookup"><span data-stu-id="a0189-122">**Checksum**</span></span> <br/> |<span data-ttu-id="a0189-123">целое</span><span class="sxs-lookup"><span data-stu-id="a0189-123">int</span></span>  <br/> ||<span data-ttu-id="a0189-124">Контрольная сумма для Конференцеури.</span><span class="sxs-lookup"><span data-stu-id="a0189-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="a0189-125">Используется для увеличения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a0189-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="a0189-126">**уритипеид**</span><span class="sxs-lookup"><span data-stu-id="a0189-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="a0189-127">целое</span><span class="sxs-lookup"><span data-stu-id="a0189-127">int</span></span>  <br/> |<span data-ttu-id="a0189-128">Другом</span><span class="sxs-lookup"><span data-stu-id="a0189-128">Foreign</span></span>  <br/> |<span data-ttu-id="a0189-129">Тип URI, например conf: чат для Конференции с помощью мгновенных сообщений или conf: аудио-видео для голосовой и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="a0189-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="a0189-130">Более подробную информацию вы увидите в таблице [уритипес Table](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="a0189-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

