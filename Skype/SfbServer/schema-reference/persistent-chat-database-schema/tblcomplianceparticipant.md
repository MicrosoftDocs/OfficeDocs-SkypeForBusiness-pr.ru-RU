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
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295463"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="951a3-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="951a3-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="951a3-104">ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.</span><span class="sxs-lookup"><span data-stu-id="951a3-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="951a3-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="951a3-105">**Columns**</span></span>

|<span data-ttu-id="951a3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="951a3-106">**Column**</span></span>|<span data-ttu-id="951a3-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="951a3-107">**Type**</span></span>|<span data-ttu-id="951a3-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="951a3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="951a3-109">Чаннелури</span><span class="sxs-lookup"><span data-stu-id="951a3-109">channelUri</span></span>  <br/> |<span data-ttu-id="951a3-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="951a3-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="951a3-111">Универсальный код ресурса (URI) канала.</span><span class="sxs-lookup"><span data-stu-id="951a3-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="951a3-112">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="951a3-112">userId</span></span>  <br/> |<span data-ttu-id="951a3-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="951a3-113">int, not null</span></span>  <br/> |<span data-ttu-id="951a3-114">Идентификатор участника (соответствующий таблице ТблпринЦипал. Принид).</span><span class="sxs-lookup"><span data-stu-id="951a3-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="951a3-115">Жоинедат</span><span class="sxs-lookup"><span data-stu-id="951a3-115">joinedAt</span></span>  <br/> |<span data-ttu-id="951a3-116">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="951a3-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="951a3-117">Метка времени присоединения к событию.</span><span class="sxs-lookup"><span data-stu-id="951a3-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="951a3-118">Партедат</span><span class="sxs-lookup"><span data-stu-id="951a3-118">partedAt</span></span>  <br/> |<span data-ttu-id="951a3-119">bigint</span><span class="sxs-lookup"><span data-stu-id="951a3-119">bigint</span></span>  <br/> |<span data-ttu-id="951a3-120">NULL, если участник все еще присоединен.</span><span class="sxs-lookup"><span data-stu-id="951a3-120">Null if participant is still joined.</span></span> <span data-ttu-id="951a3-121">Метка времени события выхода канала, если значение не равно null.</span><span class="sxs-lookup"><span data-stu-id="951a3-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="951a3-122">Эти записи в конечном итоге удаляются, когда все переводчики обрабатывают событие.</span><span class="sxs-lookup"><span data-stu-id="951a3-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="951a3-123">Усерури</span><span class="sxs-lookup"><span data-stu-id="951a3-123">userUri</span></span>  <br/> |<span data-ttu-id="951a3-124">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="951a3-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="951a3-125">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="951a3-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="951a3-126">Серверид</span><span class="sxs-lookup"><span data-stu-id="951a3-126">serverID</span></span>  <br/> |<span data-ttu-id="951a3-127">целое</span><span class="sxs-lookup"><span data-stu-id="951a3-127">int</span></span>  <br/> |<span data-ttu-id="951a3-128">Идентификация сервера (как в таблице Тблсерверидентити. Серверид).</span><span class="sxs-lookup"><span data-stu-id="951a3-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="951a3-129">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="951a3-129">sessionId</span></span>  <br/> |<span data-ttu-id="951a3-130">bigint</span><span class="sxs-lookup"><span data-stu-id="951a3-130">bigint</span></span>  <br/> |<span data-ttu-id="951a3-131">Сеанс сервера.</span><span class="sxs-lookup"><span data-stu-id="951a3-131">Server session.</span></span> <span data-ttu-id="951a3-132">Это случайное число, которое генерируется каждый раз, когда запускается служба чата.</span><span class="sxs-lookup"><span data-stu-id="951a3-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="951a3-133">Она используется для различения сеансов в целях идентификации потерянных участников.</span><span class="sxs-lookup"><span data-stu-id="951a3-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="951a3-134">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="951a3-134">**Key**</span></span>

|<span data-ttu-id="951a3-135">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="951a3-135">**Column**</span></span>|<span data-ttu-id="951a3-136">**Описание**</span><span class="sxs-lookup"><span data-stu-id="951a3-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="951a3-137">\<Чаннелури, userId, Жоинедат\></span><span class="sxs-lookup"><span data-stu-id="951a3-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="951a3-138">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="951a3-138">Primary key.</span></span>  <br/> |
   

