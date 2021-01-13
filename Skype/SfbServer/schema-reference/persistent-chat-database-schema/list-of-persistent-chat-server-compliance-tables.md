---
title: Список таблиц соответствия для сервера сохраняемого чата в Skype для бизнеса Server
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
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных соответствия сохраняемого чата состоит из следующих таблиц.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813059"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="25fd9-103">Список таблиц соответствия для сервера сохраняемого чата в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="25fd9-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="25fd9-104">Схема базы данных соответствия сохраняемого чата состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="25fd9-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="25fd9-105">Список таблиц соблюдения требований для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="25fd9-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="25fd9-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="25fd9-106">**Table**</span></span>|<span data-ttu-id="25fd9-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="25fd9-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="25fd9-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="25fd9-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="25fd9-109">Содержит события соответствия, которые еще не были обработаны настроенным адаптером.</span><span class="sxs-lookup"><span data-stu-id="25fd9-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="25fd9-110">Эта таблица содержит события, связанные с сохраняемого чата, такие как сообщения чата и загрузка файлов.</span><span class="sxs-lookup"><span data-stu-id="25fd9-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="25fd9-111">(События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="25fd9-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="25fd9-112">(Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="25fd9-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="25fd9-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="25fd9-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="25fd9-114">Содержит серверы, обработавшие события соответствия.</span><span class="sxs-lookup"><span data-stu-id="25fd9-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="25fd9-115">Эта таблица тесно связана с таблицей tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="25fd9-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="25fd9-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="25fd9-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="25fd9-117">Содержит сведения о текущих участниках по службам чата и серверам.</span><span class="sxs-lookup"><span data-stu-id="25fd9-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="25fd9-118">Она поддерживается на основе событий join и part compliance, полученных от службы сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="25fd9-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="25fd9-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="25fd9-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="25fd9-120">Содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="25fd9-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

