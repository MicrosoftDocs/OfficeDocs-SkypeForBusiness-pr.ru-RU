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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213034"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="be2f2-104">Таблица imreportsummary в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="be2f2-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="be2f2-105">В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации.</span><span class="sxs-lookup"><span data-stu-id="be2f2-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="be2f2-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be2f2-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="be2f2-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="be2f2-107">**Column**</span></span>|<span data-ttu-id="be2f2-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="be2f2-108">**Data Type**</span></span>|<span data-ttu-id="be2f2-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="be2f2-109">**Key/Index**</span></span>|<span data-ttu-id="be2f2-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="be2f2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be2f2-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="be2f2-111">**StartTime**</span></span> <br/> |<span data-ttu-id="be2f2-112">datetime</span><span class="sxs-lookup"><span data-stu-id="be2f2-112">datetime</span></span>  <br/> |<span data-ttu-id="be2f2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="be2f2-113">Primary</span></span>  <br/> |<span data-ttu-id="be2f2-114">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="be2f2-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="be2f2-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="be2f2-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="be2f2-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="be2f2-116">char(1)</span></span>  <br/> |<span data-ttu-id="be2f2-117">Primary</span><span class="sxs-lookup"><span data-stu-id="be2f2-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="be2f2-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="be2f2-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="be2f2-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="be2f2-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="be2f2-120">Primary</span><span class="sxs-lookup"><span data-stu-id="be2f2-120">Primary</span></span>  <br/> |<span data-ttu-id="be2f2-121">Полное доменное имя пула, в котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="be2f2-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="be2f2-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="be2f2-122">**AuthType**</span></span> <br/> |<span data-ttu-id="be2f2-123">целое</span><span class="sxs-lookup"><span data-stu-id="be2f2-123">int</span></span>  <br/> |<span data-ttu-id="be2f2-124">Primary</span><span class="sxs-lookup"><span data-stu-id="be2f2-124">Primary</span></span>  <br/> |<span data-ttu-id="be2f2-125">Приоритет вызова (например, срочные или не срочный).</span><span class="sxs-lookup"><span data-stu-id="be2f2-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="be2f2-126">Сведения о приоритет хранятся в [Таблица CallPriorities в Скайп для Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="be2f2-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="be2f2-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="be2f2-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="be2f2-128">bigint</span><span class="sxs-lookup"><span data-stu-id="be2f2-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="be2f2-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="be2f2-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="be2f2-130">bigint</span><span class="sxs-lookup"><span data-stu-id="be2f2-130">bigint</span></span>  <br/> ||<span data-ttu-id="be2f2-131">Общее количество мгновенных сообщений, отправленных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="be2f2-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

