---
title: Таблица UriTypes
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
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Таблица UriTypes содержит различные типы URI (идентификатор единого ресурса), отслеживаемого в Skype для бизнеса Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831689"
---
# <a name="uritypes-table"></a><span data-ttu-id="39ede-103">Таблица UriTypes</span><span class="sxs-lookup"><span data-stu-id="39ede-103">UriTypes table</span></span>
 
<span data-ttu-id="39ede-104">Таблица UriTypes содержит различные типы URI (идентификатор единого ресурса), отслеживаемого в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="39ede-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="39ede-105">После создания базы данных CDR создаются две записи, которые представляют PhoneUri и UserUri, и записи, созданные после этого, динамически назначены UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="39ede-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="39ede-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="39ede-106">**Column**</span></span>|<span data-ttu-id="39ede-107">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="39ede-107">**Data Type**</span></span>|<span data-ttu-id="39ede-108">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="39ede-108">**Key/Index**</span></span>|<span data-ttu-id="39ede-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="39ede-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39ede-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="39ede-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="39ede-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="39ede-111">tinyint</span></span>  <br/> |<span data-ttu-id="39ede-112">Primary</span><span class="sxs-lookup"><span data-stu-id="39ede-112">Primary</span></span>  <br/> |<span data-ttu-id="39ede-113">Уникальный идентификатор типа URI.</span><span class="sxs-lookup"><span data-stu-id="39ede-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="39ede-114">Возможные значения — от 0 до 255</span><span class="sxs-lookup"><span data-stu-id="39ede-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="39ede-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="39ede-115">**UriType**</span></span> <br/> |<span data-ttu-id="39ede-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="39ede-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="39ede-117">Описания различных типов URI.</span><span class="sxs-lookup"><span data-stu-id="39ede-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="39ede-118">Предварительно назначены следующие значения:</span><span class="sxs-lookup"><span data-stu-id="39ede-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="39ede-119">1 — URI телефона</span><span class="sxs-lookup"><span data-stu-id="39ede-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="39ede-120">0 — URI пользователя</span><span class="sxs-lookup"><span data-stu-id="39ede-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="39ede-121">Другие возможные типы:</span><span class="sxs-lookup"><span data-stu-id="39ede-121">Other possible types include:</span></span> <br/><span data-ttu-id="39ede-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="39ede-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="39ede-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="39ede-123">conf:audio-video</span></span><br/> <span data-ttu-id="39ede-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="39ede-124">conf:chat</span></span><br/>    <span data-ttu-id="39ede-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="39ede-125">conf:focus</span></span><br/>   <span data-ttu-id="39ede-126">mras</span><span class="sxs-lookup"><span data-stu-id="39ede-126">mras</span></span><br/>
