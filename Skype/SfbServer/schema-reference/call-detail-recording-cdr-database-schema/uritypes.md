---
title: Таблица UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Таблица UriTypes содержит различные типы URI (универсальный код ресурса), отслеживаемые в Скайп для Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212763"
---
# <a name="uritypes-table"></a><span data-ttu-id="f7ea3-103">Таблица UriTypes</span><span class="sxs-lookup"><span data-stu-id="f7ea3-103">UriTypes table</span></span>
 
<span data-ttu-id="f7ea3-104">Таблица UriTypes содержит различные типы URI (универсальный код ресурса), отслеживаемые в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="f7ea3-105">При создании базы данных регистрации Вызовов, создаются две записи для представления PhoneUri и UserUri и записей, создаваемых после динамически назначены UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="f7ea3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f7ea3-106">**Column**</span></span>|<span data-ttu-id="f7ea3-107">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="f7ea3-107">**Data Type**</span></span>|<span data-ttu-id="f7ea3-108">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="f7ea3-108">**Key/Index**</span></span>|<span data-ttu-id="f7ea3-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="f7ea3-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f7ea3-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="f7ea3-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="f7ea3-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="f7ea3-111">tinyint</span></span>  <br/> |<span data-ttu-id="f7ea3-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f7ea3-112">Primary</span></span>  <br/> |<span data-ttu-id="f7ea3-113">Уникальный идентификатор, назначенный типа URI.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="f7ea3-114">Допустимые значения — от 0 до 255</span><span class="sxs-lookup"><span data-stu-id="f7ea3-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="f7ea3-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="f7ea3-115">**UriType**</span></span> <br/> |<span data-ttu-id="f7ea3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f7ea3-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="f7ea3-117">Описание различных типов URI.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="f7ea3-118">Назначенный доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f7ea3-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="f7ea3-119">1 — Uri телефона</span><span class="sxs-lookup"><span data-stu-id="f7ea3-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="f7ea3-120">0 — Uri пользователя</span><span class="sxs-lookup"><span data-stu-id="f7ea3-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="f7ea3-121">Другие возможные типы:</span><span class="sxs-lookup"><span data-stu-id="f7ea3-121">Other possible types include:</span></span> <br/><span data-ttu-id="f7ea3-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="f7ea3-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="f7ea3-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="f7ea3-123">conf:audio-video</span></span><br/> <span data-ttu-id="f7ea3-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="f7ea3-124">conf:chat</span></span><br/>    <span data-ttu-id="f7ea3-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="f7ea3-125">conf:focus</span></span><br/>   <span data-ttu-id="f7ea3-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="f7ea3-126">mras</span></span><br/>
