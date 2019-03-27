---
title: Таблица imreportsummary в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881024"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c8231-104">Таблица imreportsummary в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c8231-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c8231-105">В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации.</span><span class="sxs-lookup"><span data-stu-id="c8231-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="c8231-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8231-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c8231-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c8231-107">**Column**</span></span>|<span data-ttu-id="c8231-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c8231-108">**Data Type**</span></span>|<span data-ttu-id="c8231-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="c8231-109">**Key/Index**</span></span>|<span data-ttu-id="c8231-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c8231-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c8231-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="c8231-111">**StartTime**</span></span> <br/> |<span data-ttu-id="c8231-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c8231-112">datetime</span></span>  <br/> |<span data-ttu-id="c8231-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c8231-113">Primary</span></span>  <br/> |<span data-ttu-id="c8231-114">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c8231-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="c8231-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="c8231-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="c8231-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="c8231-116">char(1)</span></span>  <br/> |<span data-ttu-id="c8231-117">Primary</span><span class="sxs-lookup"><span data-stu-id="c8231-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="c8231-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="c8231-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="c8231-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="c8231-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="c8231-120">Primary</span><span class="sxs-lookup"><span data-stu-id="c8231-120">Primary</span></span>  <br/> |<span data-ttu-id="c8231-121">Полное доменное имя пула, в котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="c8231-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="c8231-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="c8231-122">**AuthType**</span></span> <br/> |<span data-ttu-id="c8231-123">целое</span><span class="sxs-lookup"><span data-stu-id="c8231-123">int</span></span>  <br/> |<span data-ttu-id="c8231-124">Primary</span><span class="sxs-lookup"><span data-stu-id="c8231-124">Primary</span></span>  <br/> |<span data-ttu-id="c8231-125">Приоритет вызова (например, срочные или не срочный).</span><span class="sxs-lookup"><span data-stu-id="c8231-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="c8231-126">Сведения о приоритет хранятся в [Таблица CallPriorities в Скайп для Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="c8231-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="c8231-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="c8231-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="c8231-128">bigint</span><span class="sxs-lookup"><span data-stu-id="c8231-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="c8231-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="c8231-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="c8231-130">bigint</span><span class="sxs-lookup"><span data-stu-id="c8231-130">bigint</span></span>  <br/> ||<span data-ttu-id="c8231-131">Общее количество мгновенных сообщений, отправленных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="c8231-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

