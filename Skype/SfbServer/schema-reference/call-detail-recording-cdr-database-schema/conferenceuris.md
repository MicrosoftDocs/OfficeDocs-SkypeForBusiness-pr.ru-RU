---
title: Таблица ConferenceUris в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: В таблице ConfereneUris представляет собой вспомогательную таблицу, в которой хранится список различных конференции URI, которые участвовали в сеансах конференц записаны в базе данных. Каждая запись в таблице представляет одну URI конференции.
ms.openlocfilehash: 70cb3ccecf1c63dd128cbffd6ac205e77c771835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901068"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d4def-104">Таблица ConferenceUris в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d4def-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d4def-105">В таблице ConfereneUris представляет собой вспомогательную таблицу, в которой хранится список различных конференции URI, которые участвовали в сеансах конференц записаны в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d4def-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="d4def-106">Каждая запись в таблице представляет одну URI конференции.</span><span class="sxs-lookup"><span data-stu-id="d4def-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="d4def-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d4def-107">**Column**</span></span>|<span data-ttu-id="d4def-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d4def-108">**Data Type**</span></span>|<span data-ttu-id="d4def-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d4def-109">**Key/Index**</span></span>|<span data-ttu-id="d4def-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d4def-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d4def-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d4def-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d4def-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d4def-112">datetime</span></span>  <br/> |<span data-ttu-id="d4def-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d4def-113">Primary</span></span>  <br/> |<span data-ttu-id="d4def-114">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d4def-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="d4def-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="d4def-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="d4def-116">целое</span><span class="sxs-lookup"><span data-stu-id="d4def-116">int</span></span>  <br/> |<span data-ttu-id="d4def-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d4def-117">Primary</span></span>  <br/> |<span data-ttu-id="d4def-118">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="d4def-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="d4def-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="d4def-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="d4def-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d4def-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="d4def-121">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="d4def-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="d4def-122">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="d4def-122">**Checksum**</span></span> <br/> |<span data-ttu-id="d4def-123">целое</span><span class="sxs-lookup"><span data-stu-id="d4def-123">int</span></span>  <br/> ||<span data-ttu-id="d4def-124">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="d4def-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="d4def-125">Используется для ускоряет базы данных поиска.</span><span class="sxs-lookup"><span data-stu-id="d4def-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="d4def-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="d4def-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="d4def-127">целое</span><span class="sxs-lookup"><span data-stu-id="d4def-127">int</span></span>  <br/> |<span data-ttu-id="d4def-128">Внешний</span><span class="sxs-lookup"><span data-stu-id="d4def-128">Foreign</span></span>  <br/> |<span data-ttu-id="d4def-129">Тип URI, например conf:chat для обмена Мгновенными сообщениями или conf:audio-видео для аудиовизуальной конференции.</span><span class="sxs-lookup"><span data-stu-id="d4def-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="d4def-130">В таблице [UriTypes таблицы](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="d4def-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

