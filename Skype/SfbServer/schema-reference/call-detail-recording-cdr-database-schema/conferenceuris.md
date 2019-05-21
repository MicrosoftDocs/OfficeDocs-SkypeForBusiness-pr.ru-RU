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
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Таблица Конференеурис является вспомогательной таблицей, в которой хранится список различных URI конференций, участвующих в сеансах конференц-связи, записанных в базу данных. Каждая запись в таблице представляет один URI конференции.
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296394"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0e6d7-104">Таблица Конференцеурис в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e6d7-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e6d7-105">Таблица Конференеурис является вспомогательной таблицей, в которой хранится список различных URI конференций, участвующих в сеансах конференц-связи, записанных в базу данных.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="0e6d7-106">Каждая запись в таблице представляет один URI конференции.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="0e6d7-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-107">**Column**</span></span>|<span data-ttu-id="0e6d7-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-108">**Data Type**</span></span>|<span data-ttu-id="0e6d7-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-109">**Key/Index**</span></span>|<span data-ttu-id="0e6d7-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e6d7-111">**Некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0e6d7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0e6d7-112">datetime</span></span>  <br/> |<span data-ttu-id="0e6d7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0e6d7-113">Primary</span></span>  <br/> |<span data-ttu-id="0e6d7-114">Метка времени, используемая в качестве внутренней.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="0e6d7-115">**Конференцеуриид**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="0e6d7-116">целое</span><span class="sxs-lookup"><span data-stu-id="0e6d7-116">int</span></span>  <br/> |<span data-ttu-id="0e6d7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="0e6d7-117">Primary</span></span>  <br/> |<span data-ttu-id="0e6d7-118">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="0e6d7-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="0e6d7-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0e6d7-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="0e6d7-121">Универсальный код ресурса (URI) Конференции.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="0e6d7-122">**Счет**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-122">**Checksum**</span></span> <br/> |<span data-ttu-id="0e6d7-123">целое</span><span class="sxs-lookup"><span data-stu-id="0e6d7-123">int</span></span>  <br/> ||<span data-ttu-id="0e6d7-124">Контрольная сумма для Конференцеури.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="0e6d7-125">Используется для увеличения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="0e6d7-126">**Уритипеид**</span><span class="sxs-lookup"><span data-stu-id="0e6d7-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="0e6d7-127">целое</span><span class="sxs-lookup"><span data-stu-id="0e6d7-127">int</span></span>  <br/> |<span data-ttu-id="0e6d7-128">Другом</span><span class="sxs-lookup"><span data-stu-id="0e6d7-128">Foreign</span></span>  <br/> |<span data-ttu-id="0e6d7-129">Тип URI, например conf: чат для Конференции с помощью мгновенных сообщений или conf: аудио-видео для голосовой и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="0e6d7-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="0e6d7-130">Более подробную информацию вы увидите в таблице [уритипес Table](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="0e6d7-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

