---
title: Таблица UserAgent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799939"
---
# <a name="useragent-table"></a><span data-ttu-id="ae07a-104">Таблица UserAgent</span><span class="sxs-lookup"><span data-stu-id="ae07a-104">UserAgent table</span></span>
 
<span data-ttu-id="ae07a-105">Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ae07a-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ae07a-106">Каждая запись в таблице представляет одного агента пользователя</span><span class="sxs-lookup"><span data-stu-id="ae07a-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="ae07a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ae07a-107">**Column**</span></span>|<span data-ttu-id="ae07a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ae07a-108">**Data Type**</span></span>|<span data-ttu-id="ae07a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ae07a-109">**Key/Index**</span></span>|<span data-ttu-id="ae07a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ae07a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae07a-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="ae07a-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="ae07a-112">int</span><span class="sxs-lookup"><span data-stu-id="ae07a-112">int</span></span>  <br/> |<span data-ttu-id="ae07a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ae07a-113">Primary</span></span>  <br/> |<span data-ttu-id="ae07a-114">Уникальное число, идентифицирующее этот агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae07a-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="ae07a-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="ae07a-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="ae07a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ae07a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ae07a-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="ae07a-117">Unique</span></span>  <br/> |<span data-ttu-id="ae07a-118">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae07a-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="ae07a-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="ae07a-119">**UAType**</span></span> <br/> |<span data-ttu-id="ae07a-120">smallint</span><span class="sxs-lookup"><span data-stu-id="ae07a-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="ae07a-121">1 — сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="ae07a-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="ae07a-122">2 — сервер A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="ae07a-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="ae07a-123">4 — Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ae07a-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="ae07a-124">8 — IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="ae07a-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="ae07a-125">16 — консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="ae07a-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="ae07a-126">32 — это средство проверки развертывания (DVT).</span><span class="sxs-lookup"><span data-stu-id="ae07a-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="ae07a-127">64 — Skype для бизнеса Server на компьютерах Macintosh.</span><span class="sxs-lookup"><span data-stu-id="ae07a-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="ae07a-128">128 — помощник skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ae07a-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="ae07a-129">256 — служба объявлений для conferencing.</span><span class="sxs-lookup"><span data-stu-id="ae07a-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="ae07a-130">512 — это автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="ae07a-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="ae07a-131">1024 — приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ae07a-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="ae07a-132">2048 — это внешний голосовой контроль.</span><span class="sxs-lookup"><span data-stu-id="ae07a-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

