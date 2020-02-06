---
title: Таблица мкус в Skype для бизнеса Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Таблица Мкус является вспомогательной таблицей. Каждая запись содержит сведения о одной службе конференц-связи. К ним относятся служба конференций обмена мгновенными сообщениями и служба конференц-связи с телефонным подключением (которая запускается как процессы на серверах переднего плана), а также службы "веб-конференции" и "Конференция".
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815067"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="239ff-105">Таблица мкус в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="239ff-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="239ff-106">Таблица Мкус является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="239ff-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="239ff-107">Каждая запись содержит сведения о одной службе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="239ff-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="239ff-108">К ним относятся служба конференций обмена мгновенными сообщениями и служба конференц-связи с телефонным подключением (которая запускается как процессы на серверах переднего плана), а также службы "веб-конференции" и "Конференция".</span><span class="sxs-lookup"><span data-stu-id="239ff-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="239ff-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="239ff-109">**Column**</span></span>|<span data-ttu-id="239ff-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="239ff-110">**Data Type**</span></span>|<span data-ttu-id="239ff-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="239ff-111">**Key/Index**</span></span>|<span data-ttu-id="239ff-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="239ff-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="239ff-113">**мкуид**</span><span class="sxs-lookup"><span data-stu-id="239ff-113">**McuId**</span></span> <br/> |<span data-ttu-id="239ff-114">целое</span><span class="sxs-lookup"><span data-stu-id="239ff-114">int</span></span>  <br/> |<span data-ttu-id="239ff-115">Primary</span><span class="sxs-lookup"><span data-stu-id="239ff-115">Primary</span></span>  <br/> |<span data-ttu-id="239ff-116">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="239ff-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="239ff-117">**мкуури**</span><span class="sxs-lookup"><span data-stu-id="239ff-117">**McuUri**</span></span> <br/> |<span data-ttu-id="239ff-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="239ff-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="239ff-119">**мкутипеид**</span><span class="sxs-lookup"><span data-stu-id="239ff-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="239ff-120">ининт</span><span class="sxs-lookup"><span data-stu-id="239ff-120">inyint</span></span>  <br/> | <span data-ttu-id="239ff-121">Другом</span><span class="sxs-lookup"><span data-stu-id="239ff-121">Foreign</span></span> <br/> |<span data-ttu-id="239ff-122">Тип сервера конференций, например conf: Chat (для мгновенных сообщений) или conf: аудио-видео.</span><span class="sxs-lookup"><span data-stu-id="239ff-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="239ff-123">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="239ff-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

