---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814647"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="2e5ae-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="2e5ae-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="2e5ae-104">ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="2e5ae-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="2e5ae-105">**Columns**</span></span>

|<span data-ttu-id="2e5ae-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2e5ae-106">**Column**</span></span>|<span data-ttu-id="2e5ae-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2e5ae-107">**Type**</span></span>|<span data-ttu-id="2e5ae-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2e5ae-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e5ae-109">чаннелури</span><span class="sxs-lookup"><span data-stu-id="2e5ae-109">channelUri</span></span>  <br/> |<span data-ttu-id="2e5ae-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="2e5ae-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2e5ae-111">Универсальный код ресурса (URI) канала.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="2e5ae-112">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="2e5ae-112">userId</span></span>  <br/> |<span data-ttu-id="2e5ae-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="2e5ae-113">int, not null</span></span>  <br/> |<span data-ttu-id="2e5ae-114">Идентификатор участника (соответствующий таблице ТблпринЦипал. Принид).</span><span class="sxs-lookup"><span data-stu-id="2e5ae-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="2e5ae-115">жоинедат</span><span class="sxs-lookup"><span data-stu-id="2e5ae-115">joinedAt</span></span>  <br/> |<span data-ttu-id="2e5ae-116">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="2e5ae-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="2e5ae-117">Метка времени присоединения к событию.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="2e5ae-118">партедат</span><span class="sxs-lookup"><span data-stu-id="2e5ae-118">partedAt</span></span>  <br/> |<span data-ttu-id="2e5ae-119">bigint</span><span class="sxs-lookup"><span data-stu-id="2e5ae-119">bigint</span></span>  <br/> |<span data-ttu-id="2e5ae-120">NULL, если участник все еще присоединен.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-120">Null if participant is still joined.</span></span> <span data-ttu-id="2e5ae-121">Метка времени события выхода канала, если значение не равно null.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="2e5ae-122">Эти записи в конечном итоге удаляются, когда все переводчики обрабатывают событие.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="2e5ae-123">усерури</span><span class="sxs-lookup"><span data-stu-id="2e5ae-123">userUri</span></span>  <br/> |<span data-ttu-id="2e5ae-124">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="2e5ae-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="2e5ae-125">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="2e5ae-126">серверид</span><span class="sxs-lookup"><span data-stu-id="2e5ae-126">serverID</span></span>  <br/> |<span data-ttu-id="2e5ae-127">целое</span><span class="sxs-lookup"><span data-stu-id="2e5ae-127">int</span></span>  <br/> |<span data-ttu-id="2e5ae-128">Идентификация сервера (как в таблице Тблсерверидентити. Серверид).</span><span class="sxs-lookup"><span data-stu-id="2e5ae-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="2e5ae-129">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="2e5ae-129">sessionId</span></span>  <br/> |<span data-ttu-id="2e5ae-130">bigint</span><span class="sxs-lookup"><span data-stu-id="2e5ae-130">bigint</span></span>  <br/> |<span data-ttu-id="2e5ae-131">Сеанс сервера.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-131">Server session.</span></span> <span data-ttu-id="2e5ae-132">Это случайное число, которое генерируется каждый раз, когда запускается служба чата.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="2e5ae-133">Она используется для различения сеансов в целях идентификации потерянных участников.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="2e5ae-134">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="2e5ae-134">**Key**</span></span>

|<span data-ttu-id="2e5ae-135">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2e5ae-135">**Column**</span></span>|<span data-ttu-id="2e5ae-136">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2e5ae-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e5ae-137">\<Чаннелури, userId, Жоинедат\></span><span class="sxs-lookup"><span data-stu-id="2e5ae-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="2e5ae-138">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="2e5ae-138">Primary key.</span></span>  <br/> |
   

