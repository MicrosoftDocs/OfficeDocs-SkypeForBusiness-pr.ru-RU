---
title: Таблица ConferenceUris в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816139"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8a746-104">Таблица ConferenceUris в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a746-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a746-p102">ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.</span><span class="sxs-lookup"><span data-stu-id="8a746-p102">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="8a746-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8a746-107">**Column**</span></span>|<span data-ttu-id="8a746-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8a746-108">**Data Type**</span></span>|<span data-ttu-id="8a746-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8a746-109">**Key/Index**</span></span>|<span data-ttu-id="8a746-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="8a746-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8a746-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="8a746-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8a746-112">datetime</span><span class="sxs-lookup"><span data-stu-id="8a746-112">datetime</span></span>  <br/> |<span data-ttu-id="8a746-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8a746-113">Primary</span></span>  <br/> |<span data-ttu-id="8a746-114">Метка времени; для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="8a746-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="8a746-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="8a746-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="8a746-116">int</span><span class="sxs-lookup"><span data-stu-id="8a746-116">int</span></span>  <br/> |<span data-ttu-id="8a746-117">Primary</span><span class="sxs-lookup"><span data-stu-id="8a746-117">Primary</span></span>  <br/> |<span data-ttu-id="8a746-118">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="8a746-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="8a746-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="8a746-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="8a746-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="8a746-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="8a746-121">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="8a746-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="8a746-122">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="8a746-122">**Checksum**</span></span> <br/> |<span data-ttu-id="8a746-123">int</span><span class="sxs-lookup"><span data-stu-id="8a746-123">int</span></span>  <br/> ||<span data-ttu-id="8a746-p103">Контрольная сумма ConferenceUri. Используется для повышения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8a746-p103">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="8a746-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="8a746-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="8a746-127">int</span><span class="sxs-lookup"><span data-stu-id="8a746-127">int</span></span>  <br/> |<span data-ttu-id="8a746-128">Внешняя</span><span class="sxs-lookup"><span data-stu-id="8a746-128">Foreign</span></span>  <br/> |<span data-ttu-id="8a746-129">Тип URI, например conf:chat для конференции обмена мгновенными сообщениями или conf:audio-video для аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="8a746-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="8a746-130">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="8a746-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

