---
title: Список таблиц соответствия для сервера сохраняемого чата в Скайп для Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных соответствия Persistent Chat состоит из следующих таблиц.
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874317"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="9e3ab-103">Список таблиц соответствия для сервера сохраняемого чата в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3ab-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="9e3ab-104">Схема базы данных соответствия Persistent Chat состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="9e3ab-105">Список таблиц соответствия сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9e3ab-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="9e3ab-106">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="9e3ab-106">**Table**</span></span>|<span data-ttu-id="9e3ab-107">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9e3ab-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="9e3ab-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="9e3ab-109">Содержит события соответствия требованиям, которые еще не были обработаны настроенным адаптером.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="9e3ab-110">В этой таблице содержит события, связанные с сохраняемого чата, такие как мгновенных сообщений и файлов для загрузки.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="9e3ab-111">(Участника события отслеживаются в таблице tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="9e3ab-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="9e3ab-112">(Серверы, которые обработали события в следующей таблице перечислены в таблице tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="9e3ab-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="9e3ab-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="9e3ab-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="9e3ab-114">Содержит серверы, обработавшие событие соответствия.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="9e3ab-115">В этой таблице тесно связаны с таблицей tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="9e3ab-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="9e3ab-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="9e3ab-117">Содержит текущих участников в службы чата и на сервере.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="9e3ab-118">Поддерживается на основании присоединения и часть события соответствия, полученные от службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="9e3ab-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="9e3ab-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="9e3ab-120">Содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="9e3ab-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

