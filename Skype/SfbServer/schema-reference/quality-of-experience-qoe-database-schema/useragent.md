---
title: Таблица UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один агент пользователя
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212062"
---
# <a name="useragent-table"></a><span data-ttu-id="03ae3-104">Таблица UserAgent</span><span class="sxs-lookup"><span data-stu-id="03ae3-104">UserAgent table</span></span>
 
<span data-ttu-id="03ae3-105">Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="03ae3-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="03ae3-106">Каждая запись в таблице представляет один агент пользователя</span><span class="sxs-lookup"><span data-stu-id="03ae3-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="03ae3-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="03ae3-107">**Column**</span></span>|<span data-ttu-id="03ae3-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="03ae3-108">**Data Type**</span></span>|<span data-ttu-id="03ae3-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="03ae3-109">**Key/Index**</span></span>|<span data-ttu-id="03ae3-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="03ae3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="03ae3-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="03ae3-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="03ae3-112">целое</span><span class="sxs-lookup"><span data-stu-id="03ae3-112">int</span></span>  <br/> |<span data-ttu-id="03ae3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="03ae3-113">Primary</span></span>  <br/> |<span data-ttu-id="03ae3-114">Уникальный номер, идентифицирующий этот агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="03ae3-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="03ae3-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="03ae3-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="03ae3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="03ae3-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="03ae3-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="03ae3-117">Unique</span></span>  <br/> |<span data-ttu-id="03ae3-118">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="03ae3-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="03ae3-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="03ae3-119">**UAType**</span></span> <br/> |<span data-ttu-id="03ae3-120">smallint</span><span class="sxs-lookup"><span data-stu-id="03ae3-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="03ae3-121">1 — сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="03ae3-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="03ae3-122">2-A / V Server конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="03ae3-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="03ae3-123">4 — Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="03ae3-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="03ae3-124">8 — IP-телефона.</span><span class="sxs-lookup"><span data-stu-id="03ae3-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="03ae3-125">16 — консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="03ae3-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="03ae3-126">32 — средство проверки развертывания (DVT).</span><span class="sxs-lookup"><span data-stu-id="03ae3-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="03ae3-127">64 — Скайп для Business Server на компьютерах Macintosh.</span><span class="sxs-lookup"><span data-stu-id="03ae3-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="03ae3-128">128 — Скайп для помощника Business Server.</span><span class="sxs-lookup"><span data-stu-id="03ae3-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="03ae3-129">256 — служба оповещения для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="03ae3-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="03ae3-130">512 — автосекретарь конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="03ae3-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="03ae3-131">1024 — приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="03ae3-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="03ae3-132">2048 — управление внешней голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="03ae3-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

