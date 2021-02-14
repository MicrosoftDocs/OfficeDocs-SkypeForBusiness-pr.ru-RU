---
title: Таблица IMReportSummary в Skype для бизнеса Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821529"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="bf421-104">Таблица IMReportSummary в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bf421-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bf421-105">В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации.</span><span class="sxs-lookup"><span data-stu-id="bf421-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="bf421-106">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf421-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="bf421-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bf421-107">**Column**</span></span>|<span data-ttu-id="bf421-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bf421-108">**Data Type**</span></span>|<span data-ttu-id="bf421-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bf421-109">**Key/Index**</span></span>|<span data-ttu-id="bf421-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="bf421-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf421-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="bf421-111">**StartTime**</span></span> <br/> |<span data-ttu-id="bf421-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bf421-112">datetime</span></span>  <br/> |<span data-ttu-id="bf421-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bf421-113">Primary</span></span>  <br/> |<span data-ttu-id="bf421-114">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bf421-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="bf421-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="bf421-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="bf421-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="bf421-116">char(1)</span></span>  <br/> |<span data-ttu-id="bf421-117">Primary</span><span class="sxs-lookup"><span data-stu-id="bf421-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="bf421-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="bf421-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="bf421-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="bf421-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="bf421-120">Primary</span><span class="sxs-lookup"><span data-stu-id="bf421-120">Primary</span></span>  <br/> |<span data-ttu-id="bf421-121">Полное доменное имя пула, в котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="bf421-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="bf421-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="bf421-122">**AuthType**</span></span> <br/> |<span data-ttu-id="bf421-123">int</span><span class="sxs-lookup"><span data-stu-id="bf421-123">int</span></span>  <br/> |<span data-ttu-id="bf421-124">Primary</span><span class="sxs-lookup"><span data-stu-id="bf421-124">Primary</span></span>  <br/> |<span data-ttu-id="bf421-125">Приоритет звонка (например, срочный или несрочный).</span><span class="sxs-lookup"><span data-stu-id="bf421-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="bf421-126">Сведения о приоритетах хранятся в таблице [CallPriorities в Skype для бизнеса Server 2015.](callpriorities.md)</span><span class="sxs-lookup"><span data-stu-id="bf421-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="bf421-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="bf421-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="bf421-128">bigint</span><span class="sxs-lookup"><span data-stu-id="bf421-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="bf421-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="bf421-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="bf421-130">bigint</span><span class="sxs-lookup"><span data-stu-id="bf421-130">bigint</span></span>  <br/> ||<span data-ttu-id="bf421-131">Общее число мгновенных сообщений, отправленных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="bf421-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

