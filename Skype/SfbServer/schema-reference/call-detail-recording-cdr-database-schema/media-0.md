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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: В представлении мультимедиа хранятся сведения о одном типе мультимедиа, используемом в одноранговых сеансах. Один сеанс будет представлен в таблице несколькими записями, если используется более одного типа мультимедиа. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815057"
---
# <a name="media-view"></a><span data-ttu-id="e8e98-105">Представление "мультимедиа"</span><span class="sxs-lookup"><span data-stu-id="e8e98-105">Media view</span></span>
 
<span data-ttu-id="e8e98-106">В представлении мультимедиа хранятся сведения о одном типе мультимедиа, используемом в одноранговых сеансах.</span><span class="sxs-lookup"><span data-stu-id="e8e98-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="e8e98-107">Один сеанс будет представлен в таблице несколькими записями, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e8e98-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="e8e98-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8e98-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8e98-109">Представление мультимедиа не следует использовать для расчета длительности мультимедиа для сеанса.</span><span class="sxs-lookup"><span data-stu-id="e8e98-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="e8e98-110">В этом представлении содержатся сведения о сигналах обмена мультимедийными данными в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e8e98-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="e8e98-111">Обмен мультимедийными данными выполняется запросом приглашения, а StartTime указывает время отправки приглашения. Время приглашения не обязательно означает время начала воспроизведения мультимедиа, так как средство мультимедиа запускается только после принятия сеанса.</span><span class="sxs-lookup"><span data-stu-id="e8e98-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="e8e98-112">Представление мультимедиа включает все столбцы в [представлении сессиондетаилс](sessiondetails-0.md) в дополнение к тем, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="e8e98-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="e8e98-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e8e98-113">**Column**</span></span>|<span data-ttu-id="e8e98-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e8e98-114">**Data Type**</span></span>|<span data-ttu-id="e8e98-115">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e8e98-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8e98-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="e8e98-116">**Media**</span></span> <br/> |<span data-ttu-id="e8e98-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e8e98-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e8e98-118">Тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e8e98-118">Media type.</span></span> <span data-ttu-id="e8e98-119">Для получения дополнительных сведений ознакомьтесь с [таблицей медиалист](medialist.md) .</span><span class="sxs-lookup"><span data-stu-id="e8e98-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e8e98-120">**медиастарттиме**</span><span class="sxs-lookup"><span data-stu-id="e8e98-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="e8e98-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e8e98-121">datetime</span></span>  <br/> |<span data-ttu-id="e8e98-122">Время отправки запроса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e8e98-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="e8e98-123">**медиаендтиме**</span><span class="sxs-lookup"><span data-stu-id="e8e98-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="e8e98-124">datetime</span><span class="sxs-lookup"><span data-stu-id="e8e98-124">datetime</span></span>  <br/> |<span data-ttu-id="e8e98-125">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="e8e98-125">End time of the session.</span></span>  <br/> |
   

