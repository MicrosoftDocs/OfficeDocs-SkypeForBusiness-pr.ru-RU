---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809749"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="652e1-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="652e1-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="652e1-104">Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.</span><span class="sxs-lookup"><span data-stu-id="652e1-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="652e1-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="652e1-105">**Columns**</span></span>

|<span data-ttu-id="652e1-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="652e1-106">**Column**</span></span>|<span data-ttu-id="652e1-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="652e1-107">**Type**</span></span>|<span data-ttu-id="652e1-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="652e1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="652e1-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="652e1-109">channelUri</span></span>  <br/> |<span data-ttu-id="652e1-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="652e1-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="652e1-111">Универсальный код ресурса (URI) для канала.</span><span class="sxs-lookup"><span data-stu-id="652e1-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="652e1-112">userId</span><span class="sxs-lookup"><span data-stu-id="652e1-112">userId</span></span>  <br/> |<span data-ttu-id="652e1-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="652e1-113">int, not null</span></span>  <br/> |<span data-ttu-id="652e1-114">Идентификатор участника (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="652e1-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="652e1-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="652e1-115">joinedAt</span></span>  <br/> |<span data-ttu-id="652e1-116">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="652e1-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="652e1-117">Метка времени события присоединения.</span><span class="sxs-lookup"><span data-stu-id="652e1-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="652e1-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="652e1-118">partedAt</span></span>  <br/> |<span data-ttu-id="652e1-119">bigint</span><span class="sxs-lookup"><span data-stu-id="652e1-119">bigint</span></span>  <br/> |<span data-ttu-id="652e1-p101">Null, если участник еще присоединен.Если не null, то метка времени события выхода из канала.</span><span class="sxs-lookup"><span data-stu-id="652e1-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="652e1-122">Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.</span><span class="sxs-lookup"><span data-stu-id="652e1-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="652e1-123">userUri</span><span class="sxs-lookup"><span data-stu-id="652e1-123">userUri</span></span>  <br/> |<span data-ttu-id="652e1-124">nvarchar(255), not null</span><span class="sxs-lookup"><span data-stu-id="652e1-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="652e1-125">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="652e1-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="652e1-126">serverID</span><span class="sxs-lookup"><span data-stu-id="652e1-126">serverID</span></span>  <br/> |<span data-ttu-id="652e1-127">int</span><span class="sxs-lookup"><span data-stu-id="652e1-127">int</span></span>  <br/> |<span data-ttu-id="652e1-128">Удостоверение сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="652e1-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="652e1-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="652e1-129">sessionId</span></span>  <br/> |<span data-ttu-id="652e1-130">bigint</span><span class="sxs-lookup"><span data-stu-id="652e1-130">bigint</span></span>  <br/> |<span data-ttu-id="652e1-p102">Сеанс сервера. Это произвольный номер, который создается каждый раз при запуске службы чата. Он используется, чтобы различать сеансы в целях идентификации потерянных участников.</span><span class="sxs-lookup"><span data-stu-id="652e1-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="652e1-134">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="652e1-134">**Key**</span></span>

|<span data-ttu-id="652e1-135">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="652e1-135">**Column**</span></span>|<span data-ttu-id="652e1-136">**Описание**</span><span class="sxs-lookup"><span data-stu-id="652e1-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="652e1-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="652e1-137">Primary key.</span></span>  <br/> |
   

