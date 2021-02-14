---
title: Таблица Mcus в Skype для бизнеса Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Таблица Mcus является вспомогательной. В каждой записи хранится информация об одной службе conferencing. Они могут включать службу im Conferencing и службу телефонной связи (которая работает как процессы на серверах переднего сервера), а также службу веб-службы и службу A/V Conferencing.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821429"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="bf1de-105">Таблица Mcus в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bf1de-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bf1de-106">Таблица Mcus является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="bf1de-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="bf1de-107">В каждой записи хранится информация об одной службе conferencing.</span><span class="sxs-lookup"><span data-stu-id="bf1de-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="bf1de-108">Они могут включать службу im Conferencing и службу телефонной связи (которая работает как процессы на серверах переднего сервера), а также службу веб-службы и службу A/V Conferencing.</span><span class="sxs-lookup"><span data-stu-id="bf1de-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="bf1de-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bf1de-109">**Column**</span></span>|<span data-ttu-id="bf1de-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bf1de-110">**Data Type**</span></span>|<span data-ttu-id="bf1de-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bf1de-111">**Key/Index**</span></span>|<span data-ttu-id="bf1de-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="bf1de-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf1de-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="bf1de-113">**McuId**</span></span> <br/> |<span data-ttu-id="bf1de-114">int</span><span class="sxs-lookup"><span data-stu-id="bf1de-114">int</span></span>  <br/> |<span data-ttu-id="bf1de-115">Primary</span><span class="sxs-lookup"><span data-stu-id="bf1de-115">Primary</span></span>  <br/> |<span data-ttu-id="bf1de-116">Уникальный номер, идентифицирующий этот сервер.</span><span class="sxs-lookup"><span data-stu-id="bf1de-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="bf1de-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="bf1de-117">**McuUri**</span></span> <br/> |<span data-ttu-id="bf1de-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="bf1de-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="bf1de-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="bf1de-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="bf1de-120">inyint</span><span class="sxs-lookup"><span data-stu-id="bf1de-120">inyint</span></span>  <br/> | <span data-ttu-id="bf1de-121">Внешняя</span><span class="sxs-lookup"><span data-stu-id="bf1de-121">Foreign</span></span> <br/> |<span data-ttu-id="bf1de-122">Тип сервера аудиоконференции, например conf:chat (для IMs) или conf:audio-video.</span><span class="sxs-lookup"><span data-stu-id="bf1de-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="bf1de-123">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="bf1de-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

