---
title: Таблица Mcus в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Таблица Mcus представляет собой вспомогательную таблицу. Каждая запись хранит сведения об одной службы конференц-связи. Следующие службы обмена мгновенными Сообщениями конференц-связи и служба телефонной конференц-связи (который выполняются как процессы на серверах переднего плана) и служба веб-конференций и A / службы аудио-и видеоконференциями.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212975"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="001a4-105">Таблица Mcus в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="001a4-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="001a4-106">Таблица Mcus представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="001a4-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="001a4-107">Каждая запись хранит сведения об одной службы конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="001a4-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="001a4-108">Следующие службы обмена мгновенными Сообщениями конференц-связи и служба телефонной конференц-связи (который выполняются как процессы на серверах переднего плана) и служба веб-конференций и A / службы аудио-и видеоконференциями.</span><span class="sxs-lookup"><span data-stu-id="001a4-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="001a4-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="001a4-109">**Column**</span></span>|<span data-ttu-id="001a4-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="001a4-110">**Data Type**</span></span>|<span data-ttu-id="001a4-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="001a4-111">**Key/Index**</span></span>|<span data-ttu-id="001a4-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="001a4-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="001a4-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="001a4-113">**McuId**</span></span> <br/> |<span data-ttu-id="001a4-114">целое</span><span class="sxs-lookup"><span data-stu-id="001a4-114">int</span></span>  <br/> |<span data-ttu-id="001a4-115">Primary</span><span class="sxs-lookup"><span data-stu-id="001a4-115">Primary</span></span>  <br/> |<span data-ttu-id="001a4-116">Уникальный номер, идентифицирующий этот сервер конференций.</span><span class="sxs-lookup"><span data-stu-id="001a4-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="001a4-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="001a4-117">**McuUri**</span></span> <br/> |<span data-ttu-id="001a4-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="001a4-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="001a4-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="001a4-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="001a4-120">inyint</span><span class="sxs-lookup"><span data-stu-id="001a4-120">inyint</span></span>  <br/> | <span data-ttu-id="001a4-121">Внешний</span><span class="sxs-lookup"><span data-stu-id="001a4-121">Foreign</span></span> <br/> |<span data-ttu-id="001a4-122">Тип сервера конференций, такие как conf:chat (для мгновенных сообщений) или conf:audio-видео.</span><span class="sxs-lookup"><span data-stu-id="001a4-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="001a4-123">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="001a4-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

