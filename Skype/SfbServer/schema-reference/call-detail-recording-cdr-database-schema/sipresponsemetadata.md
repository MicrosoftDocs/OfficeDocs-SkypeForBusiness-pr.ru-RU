---
title: Таблица SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809929"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="cc3a5-104">Таблица SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="cc3a5-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="cc3a5-p102">Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.</span><span class="sxs-lookup"><span data-stu-id="cc3a5-p102">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="cc3a5-107">Эта таблица была представлена в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cc3a5-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="cc3a5-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="cc3a5-108">**Column**</span></span>|<span data-ttu-id="cc3a5-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="cc3a5-109">**Data Type**</span></span>|<span data-ttu-id="cc3a5-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="cc3a5-110">**Key/Index**</span></span>|<span data-ttu-id="cc3a5-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="cc3a5-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc3a5-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="cc3a5-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="cc3a5-113">int</span><span class="sxs-lookup"><span data-stu-id="cc3a5-113">int</span></span>  <br/> |<span data-ttu-id="cc3a5-114">Primary</span><span class="sxs-lookup"><span data-stu-id="cc3a5-114">Primary</span></span>  <br/> |<span data-ttu-id="cc3a5-115">Числовое значение, которое определяет код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="cc3a5-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="cc3a5-116">**Class**</span><span class="sxs-lookup"><span data-stu-id="cc3a5-116">**Class**</span></span> <br/> |<span data-ttu-id="cc3a5-117">int</span><span class="sxs-lookup"><span data-stu-id="cc3a5-117">int</span></span>  <br/> || <span data-ttu-id="cc3a5-p103">Общая классификация кода ответа. Возможные классификации:</span><span class="sxs-lookup"><span data-stu-id="cc3a5-p103">General classification for the response code. Classifications include:</span></span> <br/>  <span data-ttu-id="cc3a5-120">1 — информационные ответы</span><span class="sxs-lookup"><span data-stu-id="cc3a5-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="cc3a5-121">2 — успешные ответы</span><span class="sxs-lookup"><span data-stu-id="cc3a5-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="cc3a5-122">3 — ответы на перенаправление</span><span class="sxs-lookup"><span data-stu-id="cc3a5-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="cc3a5-123">4 — ответы на сбои клиентов</span><span class="sxs-lookup"><span data-stu-id="cc3a5-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="cc3a5-124">5 — ответы на сбои сервера</span><span class="sxs-lookup"><span data-stu-id="cc3a5-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="cc3a5-125">6 — глобальный ответ на сбой</span><span class="sxs-lookup"><span data-stu-id="cc3a5-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="cc3a5-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cc3a5-126">**Description**</span></span> <br/> |<span data-ttu-id="cc3a5-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cc3a5-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="cc3a5-p104">Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:</span><span class="sxs-lookup"><span data-stu-id="cc3a5-p104">Description of the SIP response code. For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="cc3a5-130">Вызов перенаправляется</span><span class="sxs-lookup"><span data-stu-id="cc3a5-130">Call Is Being Forwarded</span></span>  <br/> |
   

