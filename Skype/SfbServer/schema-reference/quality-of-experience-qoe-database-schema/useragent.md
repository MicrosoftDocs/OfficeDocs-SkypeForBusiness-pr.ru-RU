---
title: Таблица UserAgent
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent является вспомогательной таблицей, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805057"
---
# <a name="useragent-table"></a><span data-ttu-id="d596f-104">Таблица UserAgent</span><span class="sxs-lookup"><span data-stu-id="d596f-104">UserAgent table</span></span>
 
<span data-ttu-id="d596f-105">Таблица UserAgent является вспомогательной таблицей, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d596f-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d596f-106">Каждая запись в таблице представляет одного агента пользователя</span><span class="sxs-lookup"><span data-stu-id="d596f-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="d596f-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d596f-107">**Column**</span></span>|<span data-ttu-id="d596f-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d596f-108">**Data Type**</span></span>|<span data-ttu-id="d596f-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d596f-109">**Key/Index**</span></span>|<span data-ttu-id="d596f-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d596f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d596f-111">**усераженткэй**</span><span class="sxs-lookup"><span data-stu-id="d596f-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="d596f-112">целое</span><span class="sxs-lookup"><span data-stu-id="d596f-112">int</span></span>  <br/> |<span data-ttu-id="d596f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d596f-113">Primary</span></span>  <br/> |<span data-ttu-id="d596f-114">Уникальный номер, идентифицирующий агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="d596f-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="d596f-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="d596f-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="d596f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d596f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d596f-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="d596f-117">Unique</span></span>  <br/> |<span data-ttu-id="d596f-118">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="d596f-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="d596f-119">**уатипе**</span><span class="sxs-lookup"><span data-stu-id="d596f-119">**UAType**</span></span> <br/> |<span data-ttu-id="d596f-120">smallint</span><span class="sxs-lookup"><span data-stu-id="d596f-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="d596f-121">1 — сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="d596f-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="d596f-122">2 — это сервер конференц-связи с/V.</span><span class="sxs-lookup"><span data-stu-id="d596f-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="d596f-123">4 — Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d596f-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="d596f-124">8 — это IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="d596f-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="d596f-125">16 — консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="d596f-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="d596f-126">32 — средство проверки развертывания (ДВТ).</span><span class="sxs-lookup"><span data-stu-id="d596f-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="d596f-127">64 — это сервер Skype для бизнеса на компьютерах Macintosh.</span><span class="sxs-lookup"><span data-stu-id="d596f-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="d596f-128">128 является помощником по Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d596f-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="d596f-129">256 является службой объявлений конференций.</span><span class="sxs-lookup"><span data-stu-id="d596f-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="d596f-130">512 — автоматический секретарь конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d596f-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="d596f-131">1024 является приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="d596f-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="d596f-132">2048 находится за пределами голосового контроля.</span><span class="sxs-lookup"><span data-stu-id="d596f-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

