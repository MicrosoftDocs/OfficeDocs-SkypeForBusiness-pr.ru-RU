---
title: Таблица sipresponsemetadata
ms.reviewer: ''
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
ms.openlocfilehash: 7b60ffff90434c341fcf15fb75ddc93ac9f26201
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212798"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="50526-104">Таблица sipresponsemetadata</span><span class="sxs-lookup"><span data-stu-id="50526-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="50526-105">SIPResponseMetaDataTable содержит список коды ответа SIP, классификации и определения каждого из этих кодов.</span><span class="sxs-lookup"><span data-stu-id="50526-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="50526-106">Эти коды создаются в ответ на события, влияния на устройствах SIP и SIP-сеансов связи; Например код ответа 403 создается при устройства SIP выполняет запрос, но сервер отклоняет на обработку этого запроса.</span><span class="sxs-lookup"><span data-stu-id="50526-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="50526-107">Эта таблица была введена в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="50526-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="50526-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="50526-108">**Column**</span></span>|<span data-ttu-id="50526-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="50526-109">**Data Type**</span></span>|<span data-ttu-id="50526-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="50526-110">**Key/Index**</span></span>|<span data-ttu-id="50526-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="50526-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50526-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="50526-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="50526-113">целое</span><span class="sxs-lookup"><span data-stu-id="50526-113">int</span></span>  <br/> |<span data-ttu-id="50526-114">Primary</span><span class="sxs-lookup"><span data-stu-id="50526-114">Primary</span></span>  <br/> |<span data-ttu-id="50526-115">Числовое значение, представляющее код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="50526-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="50526-116">**Класс**</span><span class="sxs-lookup"><span data-stu-id="50526-116">**Class**</span></span> <br/> |<span data-ttu-id="50526-117">целое</span><span class="sxs-lookup"><span data-stu-id="50526-117">int</span></span>  <br/> || <span data-ttu-id="50526-118">Общие классификации для кода ответа.</span><span class="sxs-lookup"><span data-stu-id="50526-118">General classification for the response code.</span></span> <span data-ttu-id="50526-119">Классификации строк, относятся:</span><span class="sxs-lookup"><span data-stu-id="50526-119">Classifications include:</span></span> <br/>  <span data-ttu-id="50526-120">1 — информационные ответы</span><span class="sxs-lookup"><span data-stu-id="50526-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="50526-121">2 — успешные ответы</span><span class="sxs-lookup"><span data-stu-id="50526-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="50526-122">3 - ответы перенаправления</span><span class="sxs-lookup"><span data-stu-id="50526-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="50526-123">4 - ответы сбоя клиента</span><span class="sxs-lookup"><span data-stu-id="50526-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="50526-124">5 — Ответы сбоя сервера</span><span class="sxs-lookup"><span data-stu-id="50526-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="50526-125">6 - глобального сбоя ответа</span><span class="sxs-lookup"><span data-stu-id="50526-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="50526-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="50526-126">**Description**</span></span> <br/> |<span data-ttu-id="50526-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="50526-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="50526-128">Описание код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="50526-128">Description of the SIP response code.</span></span> <span data-ttu-id="50526-129">Например код ответа 181 имеет следующее описание:</span><span class="sxs-lookup"><span data-stu-id="50526-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="50526-130">Переадресация звонка</span><span class="sxs-lookup"><span data-stu-id="50526-130">Call Is Being Forwarded</span></span>  <br/> |
   

