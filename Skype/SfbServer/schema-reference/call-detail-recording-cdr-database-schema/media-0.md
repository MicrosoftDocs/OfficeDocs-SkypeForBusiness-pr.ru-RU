---
title: Представление "мультимедиа"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: В представлении мультимедиа хранятся сведения о одном типе мультимедиа, используемом в одноранговых сеансах. Один сеанс будет представлен в таблице несколькими записями, если используется более одного типа мультимедиа. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296002"
---
# <a name="media-view"></a><span data-ttu-id="19a78-105">Представление "мультимедиа"</span><span class="sxs-lookup"><span data-stu-id="19a78-105">Media view</span></span>
 
<span data-ttu-id="19a78-106">В представлении мультимедиа хранятся сведения о одном типе мультимедиа, используемом в одноранговых сеансах.</span><span class="sxs-lookup"><span data-stu-id="19a78-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="19a78-107">Один сеанс будет представлен в таблице несколькими записями, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="19a78-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="19a78-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19a78-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19a78-109">Представление мультимедиа не следует использовать для расчета длительности мультимедиа для сеанса.</span><span class="sxs-lookup"><span data-stu-id="19a78-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="19a78-110">В этом представлении содержатся сведения о сигналах обмена мультимедийными данными в сеансе.</span><span class="sxs-lookup"><span data-stu-id="19a78-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="19a78-111">Обмен мультимедийными данными выполняется запросом приглашения, а StartTime указывает время отправки приглашения. Время приглашения не обязательно означает время начала воспроизведения мультимедиа, так как средство мультимедиа запускается только после принятия сеанса.</span><span class="sxs-lookup"><span data-stu-id="19a78-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="19a78-112">Представление мультимедиа включает все столбцы в [представлении сессиондетаилс](sessiondetails-0.md) в дополнение к тем, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="19a78-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="19a78-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="19a78-113">**Column**</span></span>|<span data-ttu-id="19a78-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="19a78-114">**Data Type**</span></span>|<span data-ttu-id="19a78-115">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="19a78-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19a78-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="19a78-116">**Media**</span></span> <br/> |<span data-ttu-id="19a78-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19a78-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="19a78-118">Тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="19a78-118">Media type.</span></span> <span data-ttu-id="19a78-119">Для получения дополнительных сведений ознакомьтесь с [таблицей медиалист](medialist.md) .</span><span class="sxs-lookup"><span data-stu-id="19a78-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="19a78-120">**Медиастарттиме**</span><span class="sxs-lookup"><span data-stu-id="19a78-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="19a78-121">datetime</span><span class="sxs-lookup"><span data-stu-id="19a78-121">datetime</span></span>  <br/> |<span data-ttu-id="19a78-122">Время отправки запроса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="19a78-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="19a78-123">**Медиаендтиме**</span><span class="sxs-lookup"><span data-stu-id="19a78-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="19a78-124">datetime</span><span class="sxs-lookup"><span data-stu-id="19a78-124">datetime</span></span>  <br/> |<span data-ttu-id="19a78-125">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="19a78-125">End time of the session.</span></span>  <br/> |
   

