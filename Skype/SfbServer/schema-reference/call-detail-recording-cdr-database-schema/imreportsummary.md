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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815147"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4def0-104">Таблица Имрепортсуммари в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="4def0-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4def0-105">Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации.</span><span class="sxs-lookup"><span data-stu-id="4def0-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="4def0-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4def0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4def0-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4def0-107">**Column**</span></span>|<span data-ttu-id="4def0-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4def0-108">**Data Type**</span></span>|<span data-ttu-id="4def0-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4def0-109">**Key/Index**</span></span>|<span data-ttu-id="4def0-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4def0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4def0-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="4def0-111">**StartTime**</span></span> <br/> |<span data-ttu-id="4def0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4def0-112">datetime</span></span>  <br/> |<span data-ttu-id="4def0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4def0-113">Primary</span></span>  <br/> |<span data-ttu-id="4def0-114">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="4def0-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="4def0-115">**тимепериод**</span><span class="sxs-lookup"><span data-stu-id="4def0-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="4def0-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="4def0-116">char(1)</span></span>  <br/> |<span data-ttu-id="4def0-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4def0-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="4def0-118">**пулфкдн**</span><span class="sxs-lookup"><span data-stu-id="4def0-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="4def0-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="4def0-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="4def0-120">Primary</span><span class="sxs-lookup"><span data-stu-id="4def0-120">Primary</span></span>  <br/> |<span data-ttu-id="4def0-121">Полное доменное имя пула, на котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="4def0-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="4def0-122">**аустипе**</span><span class="sxs-lookup"><span data-stu-id="4def0-122">**AuthType**</span></span> <br/> |<span data-ttu-id="4def0-123">целое</span><span class="sxs-lookup"><span data-stu-id="4def0-123">int</span></span>  <br/> |<span data-ttu-id="4def0-124">Primary</span><span class="sxs-lookup"><span data-stu-id="4def0-124">Primary</span></span>  <br/> |<span data-ttu-id="4def0-125">Приоритет звонка (например, срочной или несрочный).</span><span class="sxs-lookup"><span data-stu-id="4def0-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="4def0-126">Информация о приоритетах хранится в [таблице каллприоритиес в Skype для бизнеса Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="4def0-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="4def0-127">**сессионкаунт**</span><span class="sxs-lookup"><span data-stu-id="4def0-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="4def0-128">bigint</span><span class="sxs-lookup"><span data-stu-id="4def0-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="4def0-129">**мсгкаунт**</span><span class="sxs-lookup"><span data-stu-id="4def0-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="4def0-130">bigint</span><span class="sxs-lookup"><span data-stu-id="4def0-130">bigint</span></span>  <br/> ||<span data-ttu-id="4def0-131">Общее количество мгновенных сообщений, пересылаемых во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="4def0-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

