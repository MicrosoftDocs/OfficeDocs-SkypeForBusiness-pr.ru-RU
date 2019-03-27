---
title: Представление Media
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Представление Media сохранение информации о один тип носителя используется в сеансе peer-to-peer. Один сеанс может быть представлена нескольких записей в таблице, если используется более одного типа мультимедиа. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 148f74117ba42849d58e4012e4e963b3ef1b7a3c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898045"
---
# <a name="media-view"></a><span data-ttu-id="c9c99-105">Представление Media</span><span class="sxs-lookup"><span data-stu-id="c9c99-105">Media view</span></span>
 
<span data-ttu-id="c9c99-106">Представление Media сохранение информации о один тип носителя используется в сеансе peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="c9c99-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="c9c99-107">Один сеанс может быть представлена нескольких записей в таблице, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c9c99-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="c9c99-108">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9c99-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9c99-109">Представление Media не должен использоваться для расчета продолжительность мультимедиа для сеанса.</span><span class="sxs-lookup"><span data-stu-id="c9c99-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="c9c99-110">Это представление содержит передачи сведений exchange мультимедиа в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c9c99-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="c9c99-111">Мультимедиа exchange, это делается путем запроса INVITE и StartTime указывает время отправки ПРИГЛАШЕНИЯ в работе. Время пригласить не означает, что время начала мультимедиа из-за мультимедиа начинается только после принятия сеанса.</span><span class="sxs-lookup"><span data-stu-id="c9c99-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="c9c99-112">Представление Media содержит все столбцы [SessionDetails view](sessiondetails-0.md) Кроме перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="c9c99-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="c9c99-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c9c99-113">**Column**</span></span>|<span data-ttu-id="c9c99-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c9c99-114">**Data Type**</span></span>|<span data-ttu-id="c9c99-115">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c9c99-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9c99-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="c9c99-116">**Media**</span></span> <br/> |<span data-ttu-id="c9c99-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c9c99-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c9c99-118">Тип носителя.</span><span class="sxs-lookup"><span data-stu-id="c9c99-118">Media type.</span></span> <span data-ttu-id="c9c99-119">[Таблица MediaList](medialist.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="c9c99-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c9c99-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="c9c99-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="c9c99-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c9c99-121">datetime</span></span>  <br/> |<span data-ttu-id="c9c99-122">Время отправки запроса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c9c99-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="c9c99-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="c9c99-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="c9c99-124">datetime</span><span class="sxs-lookup"><span data-stu-id="c9c99-124">datetime</span></span>  <br/> |<span data-ttu-id="c9c99-125">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="c9c99-125">End time of the session.</span></span>  <br/> |
   

