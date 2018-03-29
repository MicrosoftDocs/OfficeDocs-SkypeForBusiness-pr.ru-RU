---
title: Таблица imreportsummary в Скайп для Business Server 2015
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
ms.openlocfilehash: f716a7406f4cf3562e2fa9244e8a766ef8537f53
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3f236-104">Таблица imreportsummary в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3f236-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3f236-105">В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации.</span><span class="sxs-lookup"><span data-stu-id="3f236-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="3f236-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f236-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3f236-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3f236-107">**Column**</span></span>|<span data-ttu-id="3f236-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3f236-108">**Data Type**</span></span>|<span data-ttu-id="3f236-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="3f236-109">**Key/Index**</span></span>|<span data-ttu-id="3f236-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="3f236-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f236-111">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="3f236-111">**StartTime**</span></span> <br/> |<span data-ttu-id="3f236-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3f236-112">datetime</span></span>  <br/> |<span data-ttu-id="3f236-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3f236-113">Primary</span></span>  <br/> |<span data-ttu-id="3f236-114">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="3f236-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="3f236-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="3f236-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="3f236-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="3f236-116">char(1)</span></span>  <br/> |<span data-ttu-id="3f236-117">Primary</span><span class="sxs-lookup"><span data-stu-id="3f236-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="3f236-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="3f236-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="3f236-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="3f236-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="3f236-120">Primary</span><span class="sxs-lookup"><span data-stu-id="3f236-120">Primary</span></span>  <br/> |<span data-ttu-id="3f236-121">Полное доменное имя пула, в котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="3f236-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="3f236-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="3f236-122">**AuthType**</span></span> <br/> |<span data-ttu-id="3f236-123">целое</span><span class="sxs-lookup"><span data-stu-id="3f236-123">int</span></span>  <br/> |<span data-ttu-id="3f236-124">Primary</span><span class="sxs-lookup"><span data-stu-id="3f236-124">Primary</span></span>  <br/> |<span data-ttu-id="3f236-125">Приоритет вызова (например, срочные или не срочный).</span><span class="sxs-lookup"><span data-stu-id="3f236-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="3f236-126">Сведения о приоритет хранятся в [Таблица CallPriorities в Скайп для Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="3f236-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="3f236-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="3f236-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="3f236-128">bigint</span><span class="sxs-lookup"><span data-stu-id="3f236-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="3f236-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="3f236-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="3f236-130">bigint</span><span class="sxs-lookup"><span data-stu-id="3f236-130">bigint</span></span>  <br/> ||<span data-ttu-id="3f236-131">Общее количество мгновенных сообщений, отправленных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="3f236-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

