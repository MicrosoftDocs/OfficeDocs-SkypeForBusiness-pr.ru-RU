---
title: Таблица imreportsummary в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901047"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6b1e6-104">Таблица imreportsummary в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6b1e6-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6b1e6-105">В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации.</span><span class="sxs-lookup"><span data-stu-id="6b1e6-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="6b1e6-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b1e6-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6b1e6-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-107">**Column**</span></span>|<span data-ttu-id="6b1e6-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-108">**Data Type**</span></span>|<span data-ttu-id="6b1e6-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-109">**Key/Index**</span></span>|<span data-ttu-id="6b1e6-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b1e6-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-111">**StartTime**</span></span> <br/> |<span data-ttu-id="6b1e6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6b1e6-112">datetime</span></span>  <br/> |<span data-ttu-id="6b1e6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6b1e6-113">Primary</span></span>  <br/> |<span data-ttu-id="6b1e6-114">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="6b1e6-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="6b1e6-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="6b1e6-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="6b1e6-116">char(1)</span></span>  <br/> |<span data-ttu-id="6b1e6-117">Primary</span><span class="sxs-lookup"><span data-stu-id="6b1e6-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="6b1e6-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="6b1e6-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="6b1e6-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="6b1e6-120">Primary</span><span class="sxs-lookup"><span data-stu-id="6b1e6-120">Primary</span></span>  <br/> |<span data-ttu-id="6b1e6-121">Полное доменное имя пула, в котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="6b1e6-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="6b1e6-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-122">**AuthType**</span></span> <br/> |<span data-ttu-id="6b1e6-123">целое</span><span class="sxs-lookup"><span data-stu-id="6b1e6-123">int</span></span>  <br/> |<span data-ttu-id="6b1e6-124">Primary</span><span class="sxs-lookup"><span data-stu-id="6b1e6-124">Primary</span></span>  <br/> |<span data-ttu-id="6b1e6-125">Приоритет вызова (например, срочные или не срочный).</span><span class="sxs-lookup"><span data-stu-id="6b1e6-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="6b1e6-126">Сведения о приоритет хранятся в [Таблица CallPriorities в Скайп для Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="6b1e6-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="6b1e6-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="6b1e6-128">bigint</span><span class="sxs-lookup"><span data-stu-id="6b1e6-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="6b1e6-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="6b1e6-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="6b1e6-130">bigint</span><span class="sxs-lookup"><span data-stu-id="6b1e6-130">bigint</span></span>  <br/> ||<span data-ttu-id="6b1e6-131">Общее количество мгновенных сообщений, отправленных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="6b1e6-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

