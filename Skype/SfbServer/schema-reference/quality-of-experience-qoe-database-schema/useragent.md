---
title: Таблица UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один агент пользователя
ms.openlocfilehash: 432f5ccc26d790aff07f221a7ef9912d16c49499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907005"
---
# <a name="useragent-table"></a><span data-ttu-id="bb5be-104">Таблица UserAgent</span><span class="sxs-lookup"><span data-stu-id="bb5be-104">UserAgent table</span></span>
 
<span data-ttu-id="bb5be-105">Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="bb5be-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="bb5be-106">Каждая запись в таблице представляет один агент пользователя</span><span class="sxs-lookup"><span data-stu-id="bb5be-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="bb5be-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bb5be-107">**Column**</span></span>|<span data-ttu-id="bb5be-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bb5be-108">**Data Type**</span></span>|<span data-ttu-id="bb5be-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bb5be-109">**Key/Index**</span></span>|<span data-ttu-id="bb5be-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="bb5be-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb5be-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="bb5be-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="bb5be-112">целое</span><span class="sxs-lookup"><span data-stu-id="bb5be-112">int</span></span>  <br/> |<span data-ttu-id="bb5be-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bb5be-113">Primary</span></span>  <br/> |<span data-ttu-id="bb5be-114">Уникальный номер, идентифицирующий этот агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="bb5be-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="bb5be-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="bb5be-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="bb5be-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bb5be-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bb5be-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="bb5be-117">Unique</span></span>  <br/> |<span data-ttu-id="bb5be-118">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="bb5be-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="bb5be-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="bb5be-119">**UAType**</span></span> <br/> |<span data-ttu-id="bb5be-120">smallint</span><span class="sxs-lookup"><span data-stu-id="bb5be-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="bb5be-121">1 — сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="bb5be-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="bb5be-122">2-A / V Server конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bb5be-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="bb5be-123">4 — Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bb5be-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="bb5be-124">8 — IP-телефона.</span><span class="sxs-lookup"><span data-stu-id="bb5be-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="bb5be-125">16 — консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="bb5be-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="bb5be-126">32 — средство проверки развертывания (DVT).</span><span class="sxs-lookup"><span data-stu-id="bb5be-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="bb5be-127">64 — Скайп для Business Server на компьютерах Macintosh.</span><span class="sxs-lookup"><span data-stu-id="bb5be-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="bb5be-128">128 — Скайп для помощника Business Server.</span><span class="sxs-lookup"><span data-stu-id="bb5be-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="bb5be-129">256 — служба оповещения для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bb5be-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="bb5be-130">512 — автосекретарь конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bb5be-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="bb5be-131">1024 — приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="bb5be-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="bb5be-132">2048 — управление внешней голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="bb5be-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

