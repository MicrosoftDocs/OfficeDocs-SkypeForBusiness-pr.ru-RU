---
title: Таблица sipresponsemetadata
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable содержит список коды ответа SIP, классификации и определения каждого из этих кодов. Эти коды создаются в ответ на события, влияния на устройствах SIP и SIP-сеансов связи; Например код ответа 403 создается при устройства SIP выполняет запрос, но сервер отклоняет на обработку этого запроса.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="38f7d-104">Таблица sipresponsemetadata</span><span class="sxs-lookup"><span data-stu-id="38f7d-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="38f7d-105">SIPResponseMetaDataTable содержит список коды ответа SIP, классификации и определения каждого из этих кодов.</span><span class="sxs-lookup"><span data-stu-id="38f7d-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="38f7d-106">Эти коды создаются в ответ на события, влияния на устройствах SIP и SIP-сеансов связи; Например код ответа 403 создается при устройства SIP выполняет запрос, но сервер отклоняет на обработку этого запроса.</span><span class="sxs-lookup"><span data-stu-id="38f7d-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="38f7d-107">Эта таблица была введена в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38f7d-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="38f7d-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="38f7d-108">**Column**</span></span>|<span data-ttu-id="38f7d-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="38f7d-109">**Data Type**</span></span>|<span data-ttu-id="38f7d-110">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="38f7d-110">**Key/Index**</span></span>|<span data-ttu-id="38f7d-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="38f7d-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38f7d-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="38f7d-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="38f7d-113">целое</span><span class="sxs-lookup"><span data-stu-id="38f7d-113">int</span></span>  <br/> |<span data-ttu-id="38f7d-114">Primary</span><span class="sxs-lookup"><span data-stu-id="38f7d-114">Primary</span></span>  <br/> |<span data-ttu-id="38f7d-115">Числовое значение, представляющее код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="38f7d-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="38f7d-116">**Класс**</span><span class="sxs-lookup"><span data-stu-id="38f7d-116">**Class**</span></span> <br/> |<span data-ttu-id="38f7d-117">целое</span><span class="sxs-lookup"><span data-stu-id="38f7d-117">int</span></span>  <br/> || <span data-ttu-id="38f7d-118">Общие классификации для кода ответа.</span><span class="sxs-lookup"><span data-stu-id="38f7d-118">General classification for the response code.</span></span> <span data-ttu-id="38f7d-119">Классификации строк, относятся:</span><span class="sxs-lookup"><span data-stu-id="38f7d-119">Classifications include:</span></span> <br/>  <span data-ttu-id="38f7d-120">1 — информационные ответы</span><span class="sxs-lookup"><span data-stu-id="38f7d-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="38f7d-121">2 — успешные ответы</span><span class="sxs-lookup"><span data-stu-id="38f7d-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="38f7d-122">3 - ответы перенаправления</span><span class="sxs-lookup"><span data-stu-id="38f7d-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="38f7d-123">4 - ответы сбоя клиента</span><span class="sxs-lookup"><span data-stu-id="38f7d-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="38f7d-124">5 — Ответы сбоя сервера</span><span class="sxs-lookup"><span data-stu-id="38f7d-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="38f7d-125">6 - глобального сбоя ответа</span><span class="sxs-lookup"><span data-stu-id="38f7d-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="38f7d-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="38f7d-126">**Description**</span></span> <br/> |<span data-ttu-id="38f7d-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="38f7d-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="38f7d-128">Описание код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="38f7d-128">Description of the SIP response code.</span></span> <span data-ttu-id="38f7d-129">Например код ответа 181 имеет следующее описание:</span><span class="sxs-lookup"><span data-stu-id="38f7d-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="38f7d-130">Переадресация звонка</span><span class="sxs-lookup"><span data-stu-id="38f7d-130">Call Is Being Forwarded</span></span>  <br/> |
   

