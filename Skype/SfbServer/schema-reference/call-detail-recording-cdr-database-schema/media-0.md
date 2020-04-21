---
title: Представление мультимедиа
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
description: В представлении "Мультимедиа" хранятся данные об одном типе мультимедийных данных, используемых в одноранговом сеансе. Один сеанс может быть представлен несколькими записями в таблице, если используется более одного типа мультимедиа. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815057"
---
# <a name="media-view"></a><span data-ttu-id="bb9cc-105">Представление мультимедиа</span><span class="sxs-lookup"><span data-stu-id="bb9cc-105">Media view</span></span>
 
<span data-ttu-id="bb9cc-106">В представлении "Мультимедиа" хранятся данные об одном типе мультимедийных данных, используемых в одноранговом сеансе.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="bb9cc-107">Один сеанс может быть представлен несколькими записями в таблице, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="bb9cc-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb9cc-p103">Представление "Мультимедиа" не используется для расчета продолжительности воспроизведения мультимедиа в ходе сеанса. На представлении отображены сведения о сигнале для обмена мультимедиа в рамках сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а значение StartTime определяет время отправки запроса INVITE. Время приглашения может не совпадать с временем начала воспроизведения мультимедиа, поскольку воспроизведение мультимедиа начинается только после подтверждения приема сеанса.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="bb9cc-112">Представление мультимедиа содержит все столбцы в [представлении SessionDetails](sessiondetails-0.md) в дополнение к тем, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="bb9cc-113">**Column**</span><span class="sxs-lookup"><span data-stu-id="bb9cc-113">**Column**</span></span>|<span data-ttu-id="bb9cc-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bb9cc-114">**Data Type**</span></span>|<span data-ttu-id="bb9cc-115">**Details**</span><span class="sxs-lookup"><span data-stu-id="bb9cc-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb9cc-116">**Носитель**</span><span class="sxs-lookup"><span data-stu-id="bb9cc-116">**Media**</span></span> <br/> |<span data-ttu-id="bb9cc-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb9cc-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bb9cc-118">Тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-118">Media type.</span></span> <span data-ttu-id="bb9cc-119">Дополнительные сведения см. в [таблице таблица medialist](medialist.md) .</span><span class="sxs-lookup"><span data-stu-id="bb9cc-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="bb9cc-120">**медиастарттиме**</span><span class="sxs-lookup"><span data-stu-id="bb9cc-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="bb9cc-121">datetime</span><span class="sxs-lookup"><span data-stu-id="bb9cc-121">datetime</span></span>  <br/> |<span data-ttu-id="bb9cc-122">Время отправки запроса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="bb9cc-123">**медиаендтиме**</span><span class="sxs-lookup"><span data-stu-id="bb9cc-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="bb9cc-124">datetime</span><span class="sxs-lookup"><span data-stu-id="bb9cc-124">datetime</span></span>  <br/> |<span data-ttu-id="bb9cc-125">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="bb9cc-125">End time of the session.</span></span>  <br/> |
   

