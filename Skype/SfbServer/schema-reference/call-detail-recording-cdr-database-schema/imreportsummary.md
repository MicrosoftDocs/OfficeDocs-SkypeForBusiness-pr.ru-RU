---
title: Таблица Имрепортсуммари в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296128"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8d133-104">Таблица Имрепортсуммари в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d133-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d133-105">Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации.</span><span class="sxs-lookup"><span data-stu-id="8d133-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="8d133-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d133-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8d133-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8d133-107">**Column**</span></span>|<span data-ttu-id="8d133-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8d133-108">**Data Type**</span></span>|<span data-ttu-id="8d133-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8d133-109">**Key/Index**</span></span>|<span data-ttu-id="8d133-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8d133-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d133-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="8d133-111">**StartTime**</span></span> <br/> |<span data-ttu-id="8d133-112">datetime</span><span class="sxs-lookup"><span data-stu-id="8d133-112">datetime</span></span>  <br/> |<span data-ttu-id="8d133-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8d133-113">Primary</span></span>  <br/> |<span data-ttu-id="8d133-114">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8d133-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="8d133-115">**Тимепериод**</span><span class="sxs-lookup"><span data-stu-id="8d133-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="8d133-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="8d133-116">char(1)</span></span>  <br/> |<span data-ttu-id="8d133-117">Primary</span><span class="sxs-lookup"><span data-stu-id="8d133-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="8d133-118">**Пулфкдн**</span><span class="sxs-lookup"><span data-stu-id="8d133-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="8d133-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="8d133-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="8d133-120">Primary</span><span class="sxs-lookup"><span data-stu-id="8d133-120">Primary</span></span>  <br/> |<span data-ttu-id="8d133-121">Полное доменное имя пула, на котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="8d133-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="8d133-122">**Аустипе**</span><span class="sxs-lookup"><span data-stu-id="8d133-122">**AuthType**</span></span> <br/> |<span data-ttu-id="8d133-123">целое</span><span class="sxs-lookup"><span data-stu-id="8d133-123">int</span></span>  <br/> |<span data-ttu-id="8d133-124">Primary</span><span class="sxs-lookup"><span data-stu-id="8d133-124">Primary</span></span>  <br/> |<span data-ttu-id="8d133-125">Приоритет звонка (например, срочной или несрочный).</span><span class="sxs-lookup"><span data-stu-id="8d133-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="8d133-126">Информация о приоритетах хранится в [таблице каллприоритиес в Skype для бизнеса Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="8d133-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="8d133-127">**Сессионкаунт**</span><span class="sxs-lookup"><span data-stu-id="8d133-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="8d133-128">bigint</span><span class="sxs-lookup"><span data-stu-id="8d133-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="8d133-129">**Мсгкаунт**</span><span class="sxs-lookup"><span data-stu-id="8d133-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="8d133-130">bigint</span><span class="sxs-lookup"><span data-stu-id="8d133-130">bigint</span></span>  <br/> ||<span data-ttu-id="8d133-131">Общее количество мгновенных сообщений, пересылаемых во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="8d133-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

