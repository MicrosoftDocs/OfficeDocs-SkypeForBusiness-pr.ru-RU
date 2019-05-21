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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent является вспомогательной таблицей, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294588"
---
# <a name="useragent-table"></a><span data-ttu-id="cbf2c-104">Таблица UserAgent</span><span class="sxs-lookup"><span data-stu-id="cbf2c-104">UserAgent table</span></span>
 
<span data-ttu-id="cbf2c-105">Таблица UserAgent является вспомогательной таблицей, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="cbf2c-106">Каждая запись в таблице представляет одного агента пользователя</span><span class="sxs-lookup"><span data-stu-id="cbf2c-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="cbf2c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="cbf2c-107">**Column**</span></span>|<span data-ttu-id="cbf2c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="cbf2c-108">**Data Type**</span></span>|<span data-ttu-id="cbf2c-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="cbf2c-109">**Key/Index**</span></span>|<span data-ttu-id="cbf2c-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="cbf2c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbf2c-111">**Усераженткэй**</span><span class="sxs-lookup"><span data-stu-id="cbf2c-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="cbf2c-112">целое</span><span class="sxs-lookup"><span data-stu-id="cbf2c-112">int</span></span>  <br/> |<span data-ttu-id="cbf2c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cbf2c-113">Primary</span></span>  <br/> |<span data-ttu-id="cbf2c-114">Уникальный номер, идентифицирующий агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="cbf2c-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="cbf2c-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="cbf2c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbf2c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cbf2c-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="cbf2c-117">Unique</span></span>  <br/> |<span data-ttu-id="cbf2c-118">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="cbf2c-119">**Уатипе**</span><span class="sxs-lookup"><span data-stu-id="cbf2c-119">**UAType**</span></span> <br/> |<span data-ttu-id="cbf2c-120">smallint</span><span class="sxs-lookup"><span data-stu-id="cbf2c-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="cbf2c-121">1 — сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="cbf2c-122">2 — это сервер конференц-связи с/V.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="cbf2c-123">4 — Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="cbf2c-124">8 — это IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="cbf2c-125">16 — консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="cbf2c-126">32 — средство проверки развертывания (ДВТ).</span><span class="sxs-lookup"><span data-stu-id="cbf2c-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="cbf2c-127">64 — это сервер Skype для бизнеса на компьютерах Macintosh.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="cbf2c-128">128 является помощником по Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="cbf2c-129">256 является службой объявлений конференций.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="cbf2c-130">512 — автоматический секретарь конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="cbf2c-131">1024 является приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="cbf2c-132">2048 находится за пределами голосового контроля.</span><span class="sxs-lookup"><span data-stu-id="cbf2c-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

