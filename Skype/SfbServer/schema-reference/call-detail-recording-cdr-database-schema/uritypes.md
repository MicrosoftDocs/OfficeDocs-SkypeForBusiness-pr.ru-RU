---
title: Таблица UriTypes
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
ms.openlocfilehash: e21fe7d88c64acf57ad8d318a755b7fa6c73c1c2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570060"
---
# <a name="uritypes-table"></a><span data-ttu-id="c03f0-103">Таблица UriTypes</span><span class="sxs-lookup"><span data-stu-id="c03f0-103">UriTypes table</span></span>
 
<span data-ttu-id="c03f0-104">Таблица UriTypes содержит различные типы URI (универсальный код ресурса), отслеживаемые в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c03f0-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="c03f0-105">При создании базы данных регистрации Вызовов, создаются две записи для представления PhoneUri и UserUri, а другим пользователям</span><span class="sxs-lookup"><span data-stu-id="c03f0-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and others</span></span> 
  
|<span data-ttu-id="c03f0-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c03f0-106">**Column**</span></span>|<span data-ttu-id="c03f0-107">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c03f0-107">**Data Type**</span></span>|<span data-ttu-id="c03f0-108">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="c03f0-108">**Key/Index**</span></span>|<span data-ttu-id="c03f0-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c03f0-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c03f0-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="c03f0-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="c03f0-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="c03f0-111">tinyint</span></span>  <br/> |<span data-ttu-id="c03f0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c03f0-112">Primary</span></span>  <br/> |<span data-ttu-id="c03f0-113">Уникальный идентификатор, назначенный типа URI.</span><span class="sxs-lookup"><span data-stu-id="c03f0-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="c03f0-114">Допустимые значения — от 0 до 255</span><span class="sxs-lookup"><span data-stu-id="c03f0-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="c03f0-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="c03f0-115">**UriType**</span></span> <br/> |<span data-ttu-id="c03f0-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c03f0-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c03f0-117">Описание различных типов URI.</span><span class="sxs-lookup"><span data-stu-id="c03f0-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="c03f0-118">Назначенный доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c03f0-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="c03f0-119">1 — Uri телефона</span><span class="sxs-lookup"><span data-stu-id="c03f0-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="c03f0-120">0 — Uri пользователя</span><span class="sxs-lookup"><span data-stu-id="c03f0-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="c03f0-121">Другие возможные типы:</span><span class="sxs-lookup"><span data-stu-id="c03f0-121">Other possible types include:</span></span> <br/><span data-ttu-id="c03f0-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c03f0-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="c03f0-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="c03f0-123">conf:audio-video</span></span><br/> <span data-ttu-id="c03f0-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="c03f0-124">conf:chat</span></span><br/>    <span data-ttu-id="c03f0-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="c03f0-125">conf:focus</span></span><br/>   <span data-ttu-id="c03f0-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="c03f0-126">mras</span></span><br/>