---
title: Таблица UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: В таблице Уритипес содержатся различные типы URI (универсального идентификатора ресурса), отслеживаемые в Skype для бизнеса Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295750"
---
# <a name="uritypes-table"></a><span data-ttu-id="af769-103">Таблица UriTypes</span><span class="sxs-lookup"><span data-stu-id="af769-103">UriTypes table</span></span>
 
<span data-ttu-id="af769-104">В таблице Уритипес содержатся различные типы URI (универсального идентификатора ресурса), отслеживаемые в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="af769-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="af769-105">После создания базы данных CDR создаются две записи, представляющие Фонеури и Усерури, а также записи, созданные после того, как динамически назначены Уритипеид.</span><span class="sxs-lookup"><span data-stu-id="af769-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="af769-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="af769-106">**Column**</span></span>|<span data-ttu-id="af769-107">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="af769-107">**Data Type**</span></span>|<span data-ttu-id="af769-108">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="af769-108">**Key/Index**</span></span>|<span data-ttu-id="af769-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="af769-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af769-110">**Уритипеид**</span><span class="sxs-lookup"><span data-stu-id="af769-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="af769-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="af769-111">tinyint</span></span>  <br/> |<span data-ttu-id="af769-112">Primary</span><span class="sxs-lookup"><span data-stu-id="af769-112">Primary</span></span>  <br/> |<span data-ttu-id="af769-113">Уникальный идентификатор, присвоенный типу URI.</span><span class="sxs-lookup"><span data-stu-id="af769-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="af769-114">Возможные значения: от 0 до 255</span><span class="sxs-lookup"><span data-stu-id="af769-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="af769-115">**Уритипе**</span><span class="sxs-lookup"><span data-stu-id="af769-115">**UriType**</span></span> <br/> |<span data-ttu-id="af769-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="af769-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="af769-117">Описание различных типов URI.</span><span class="sxs-lookup"><span data-stu-id="af769-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="af769-118">Следующие значения предварительно назначены:</span><span class="sxs-lookup"><span data-stu-id="af769-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="af769-119">Универсальный код ресурса (URI) на 1 номер</span><span class="sxs-lookup"><span data-stu-id="af769-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="af769-120">0 — URI пользователя</span><span class="sxs-lookup"><span data-stu-id="af769-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="af769-121">Ниже перечислены другие возможные типы.</span><span class="sxs-lookup"><span data-stu-id="af769-121">Other possible types include:</span></span> <br/><span data-ttu-id="af769-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="af769-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="af769-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="af769-123">conf:audio-video</span></span><br/> <span data-ttu-id="af769-124">conf: чат</span><span class="sxs-lookup"><span data-stu-id="af769-124">conf:chat</span></span><br/>    <span data-ttu-id="af769-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="af769-125">conf:focus</span></span><br/>   <span data-ttu-id="af769-126">мрас</span><span class="sxs-lookup"><span data-stu-id="af769-126">mras</span></span><br/>
