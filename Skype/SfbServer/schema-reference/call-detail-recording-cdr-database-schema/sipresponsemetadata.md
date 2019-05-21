---
title: Таблица Сипреспонсеметадата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: В Сипреспонсеметадататабле содержится список кодов ответов SIP, а также классификация и определение каждого из этих кодов. Эти коды генерируются в ответ на события, влияющие на устройства SIP и сеансы связи SIP; Например, код ответа 403 генерируется, когда устройство SIP делает запрос, но сервер отклоняет этот запрос.
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295792"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="ca7d2-104">Таблица Сипреспонсеметадата</span><span class="sxs-lookup"><span data-stu-id="ca7d2-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="ca7d2-105">В Сипреспонсеметадататабле содержится список кодов ответов SIP, а также классификация и определение каждого из этих кодов.</span><span class="sxs-lookup"><span data-stu-id="ca7d2-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="ca7d2-106">Эти коды генерируются в ответ на события, влияющие на устройства SIP и сеансы связи SIP; Например, код ответа 403 генерируется, когда устройство SIP делает запрос, но сервер отклоняет этот запрос.</span><span class="sxs-lookup"><span data-stu-id="ca7d2-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="ca7d2-107">Эта таблица была представлена в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ca7d2-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="ca7d2-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ca7d2-108">**Column**</span></span>|<span data-ttu-id="ca7d2-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ca7d2-109">**Data Type**</span></span>|<span data-ttu-id="ca7d2-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ca7d2-110">**Key/Index**</span></span>|<span data-ttu-id="ca7d2-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ca7d2-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ca7d2-112">**Респонсекоде**</span><span class="sxs-lookup"><span data-stu-id="ca7d2-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="ca7d2-113">целое</span><span class="sxs-lookup"><span data-stu-id="ca7d2-113">int</span></span>  <br/> |<span data-ttu-id="ca7d2-114">Primary</span><span class="sxs-lookup"><span data-stu-id="ca7d2-114">Primary</span></span>  <br/> |<span data-ttu-id="ca7d2-115">Числовое значение, представляющее код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="ca7d2-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="ca7d2-116">**Классов**</span><span class="sxs-lookup"><span data-stu-id="ca7d2-116">**Class**</span></span> <br/> |<span data-ttu-id="ca7d2-117">целое</span><span class="sxs-lookup"><span data-stu-id="ca7d2-117">int</span></span>  <br/> || <span data-ttu-id="ca7d2-118">Общая классификация для кода ответа.</span><span class="sxs-lookup"><span data-stu-id="ca7d2-118">General classification for the response code.</span></span> <span data-ttu-id="ca7d2-119">Существуют следующие классификации:</span><span class="sxs-lookup"><span data-stu-id="ca7d2-119">Classifications include:</span></span> <br/>  <span data-ttu-id="ca7d2-120">1 — Информационные ответы</span><span class="sxs-lookup"><span data-stu-id="ca7d2-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="ca7d2-121">2 — успешные ответы</span><span class="sxs-lookup"><span data-stu-id="ca7d2-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="ca7d2-122">3 – Ответы на перенаправление</span><span class="sxs-lookup"><span data-stu-id="ca7d2-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="ca7d2-123">4 — Ответы на ошибки клиента</span><span class="sxs-lookup"><span data-stu-id="ca7d2-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="ca7d2-124">5-Ответы на ошибки сервера</span><span class="sxs-lookup"><span data-stu-id="ca7d2-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="ca7d2-125">6-глобальный ошибочный ответ</span><span class="sxs-lookup"><span data-stu-id="ca7d2-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="ca7d2-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ca7d2-126">**Description**</span></span> <br/> |<span data-ttu-id="ca7d2-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca7d2-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="ca7d2-128">Описание кода ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="ca7d2-128">Description of the SIP response code.</span></span> <span data-ttu-id="ca7d2-129">Например, код ответа 181 имеет следующее описание:</span><span class="sxs-lookup"><span data-stu-id="ca7d2-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="ca7d2-130">Переадресация звонка</span><span class="sxs-lookup"><span data-stu-id="ca7d2-130">Call Is Being Forwarded</span></span>  <br/> |
   

