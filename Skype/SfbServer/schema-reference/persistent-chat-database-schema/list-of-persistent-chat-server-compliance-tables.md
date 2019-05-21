---
title: Список таблиц соответствия требованиям сервера для работы с сохраняемым сервером чата в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных соответствия требованиям к сохраненным Чатам состоит из следующих таблиц.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295659"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="e3386-103">Список таблиц соответствия требованиям сервера для работы с сохраняемым сервером чата в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3386-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="e3386-104">Схема базы данных соответствия требованиям к сохраненным Чатам состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="e3386-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="e3386-105">Список таблиц соответствия требованиям сервера для работы с постоянной версией чата</span><span class="sxs-lookup"><span data-stu-id="e3386-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="e3386-106">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="e3386-106">**Table**</span></span>|<span data-ttu-id="e3386-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e3386-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e3386-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="e3386-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="e3386-109">Содержит события соответствия требованиям, которые еще не были обработаны настроенным адаптером.</span><span class="sxs-lookup"><span data-stu-id="e3386-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="e3386-110">В этой таблице содержатся сохраняемые события, связанные с чат, такие как сообщения чата и загружаемые файлы.</span><span class="sxs-lookup"><span data-stu-id="e3386-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="e3386-111">(События участников отслеживаются таблицей ТблкомплианцепартиЦипант.)</span><span class="sxs-lookup"><span data-stu-id="e3386-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="e3386-112">(Серверы, обработавшие события в этой таблице, перечислены в таблице Тблкомплианцефанаут).</span><span class="sxs-lookup"><span data-stu-id="e3386-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="e3386-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="e3386-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="e3386-114">Содержат серверы, которые обрабатывали событие соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e3386-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="e3386-115">Эта таблица тесно связана с таблицей Тблкомплианцедата.</span><span class="sxs-lookup"><span data-stu-id="e3386-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="e3386-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="e3386-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="e3386-117">Включает в себя текущих участников для каждой службы чата и для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="e3386-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="e3386-118">Она поддерживается на основе событий присоединения и частей соответствия, полученных от службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="e3386-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="e3386-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="e3386-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="e3386-120">Сведения о состоянии соответствия требованиям всего пула.</span><span class="sxs-lookup"><span data-stu-id="e3386-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

