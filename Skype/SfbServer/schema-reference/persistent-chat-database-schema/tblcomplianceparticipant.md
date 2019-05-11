---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: Таблица Complianceparticipant содержит текущих участников на канал и на каждом сервере.
ms.openlocfilehash: 6644796d88f303c6614cbd73d98224fe0e41eabb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929940"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="c6284-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="c6284-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="c6284-104">Таблица Complianceparticipant содержит текущих участников на канал и на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="c6284-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="c6284-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="c6284-105">**Columns**</span></span>

|<span data-ttu-id="c6284-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c6284-106">**Column**</span></span>|<span data-ttu-id="c6284-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c6284-107">**Type**</span></span>|<span data-ttu-id="c6284-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c6284-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6284-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="c6284-109">channelUri</span></span>  <br/> |<span data-ttu-id="c6284-110">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="c6284-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="c6284-111">Канал универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c6284-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="c6284-112">идентификатор пользователя</span><span class="sxs-lookup"><span data-stu-id="c6284-112">userId</span></span>  <br/> |<span data-ttu-id="c6284-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="c6284-113">int, not null</span></span>  <br/> |<span data-ttu-id="c6284-114">Идентификатор субъекта участника (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="c6284-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="c6284-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="c6284-115">joinedAt</span></span>  <br/> |<span data-ttu-id="c6284-116">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="c6284-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="c6284-117">Метка времени события присоединения.</span><span class="sxs-lookup"><span data-stu-id="c6284-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="c6284-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="c6284-118">partedAt</span></span>  <br/> |<span data-ttu-id="c6284-119">bigint</span><span class="sxs-lookup"><span data-stu-id="c6284-119">bigint</span></span>  <br/> |<span data-ttu-id="c6284-120">NULL, если по-прежнему присоединился к участника.</span><span class="sxs-lookup"><span data-stu-id="c6284-120">Null if participant is still joined.</span></span> <span data-ttu-id="c6284-121">Метка времени канала, отправляемых из события, если не может быть null.</span><span class="sxs-lookup"><span data-stu-id="c6284-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="c6284-122">Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.</span><span class="sxs-lookup"><span data-stu-id="c6284-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="c6284-123">userUri</span><span class="sxs-lookup"><span data-stu-id="c6284-123">userUri</span></span>  <br/> |<span data-ttu-id="c6284-124">nvarchar(255), не может быть null</span><span class="sxs-lookup"><span data-stu-id="c6284-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="c6284-125">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="c6284-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="c6284-126">Который</span><span class="sxs-lookup"><span data-stu-id="c6284-126">serverID</span></span>  <br/> |<span data-ttu-id="c6284-127">целое</span><span class="sxs-lookup"><span data-stu-id="c6284-127">int</span></span>  <br/> |<span data-ttu-id="c6284-128">Удостоверение сервера (в таблице tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="c6284-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="c6284-129">Код сеанса</span><span class="sxs-lookup"><span data-stu-id="c6284-129">sessionId</span></span>  <br/> |<span data-ttu-id="c6284-130">bigint</span><span class="sxs-lookup"><span data-stu-id="c6284-130">bigint</span></span>  <br/> |<span data-ttu-id="c6284-131">Сеанс сервера.</span><span class="sxs-lookup"><span data-stu-id="c6284-131">Server session.</span></span> <span data-ttu-id="c6284-132">Это случайное число создается каждый раз при запуске службы чата.</span><span class="sxs-lookup"><span data-stu-id="c6284-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="c6284-133">Он используется для различать сеансы для идентификации потерянных участников.</span><span class="sxs-lookup"><span data-stu-id="c6284-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="c6284-134">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="c6284-134">**Key**</span></span>

|<span data-ttu-id="c6284-135">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c6284-135">**Column**</span></span>|<span data-ttu-id="c6284-136">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c6284-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6284-137">\<channelUri, идентификатор пользователя, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="c6284-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="c6284-138">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c6284-138">Primary key.</span></span>  <br/> |
   

