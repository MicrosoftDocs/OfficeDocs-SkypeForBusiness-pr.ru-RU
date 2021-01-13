---
title: Представление мультимедиа
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: В представлении "Мультимедиа" хранятся данные об одном типе мультимедийных данных, используемых в одноранговом сеансе. Один сеанс может быть представлен несколькими записями в таблице, если используется более одного типа мультимедиа. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831794"
---
# <a name="media-view"></a><span data-ttu-id="8514e-105">Представление мультимедиа</span><span class="sxs-lookup"><span data-stu-id="8514e-105">Media view</span></span>
 
<span data-ttu-id="8514e-106">В представлении "Мультимедиа" хранятся данные об одном типе мультимедийных данных, используемых в одноранговом сеансе.</span><span class="sxs-lookup"><span data-stu-id="8514e-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="8514e-107">Один сеанс может быть представлен несколькими записями в таблице, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8514e-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="8514e-108">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8514e-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8514e-p103">Представление "Мультимедиа" не используется для расчета продолжительности воспроизведения мультимедиа в ходе сеанса. На представлении отображены сведения о сигнале для обмена мультимедиа в рамках сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а значение StartTime определяет время отправки запроса INVITE. Время приглашения может не совпадать с временем начала воспроизведения мультимедиа, поскольку воспроизведение мультимедиа начинается только после подтверждения приема сеанса.</span><span class="sxs-lookup"><span data-stu-id="8514e-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="8514e-112">Представление "Мультимедиа" содержит все столбцы в представлении [SessionDetails,](sessiondetails-0.md) а также перечисленные ниже столбцы.</span><span class="sxs-lookup"><span data-stu-id="8514e-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="8514e-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8514e-113">**Column**</span></span>|<span data-ttu-id="8514e-114">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8514e-114">**Data Type**</span></span>|<span data-ttu-id="8514e-115">**Details**</span><span class="sxs-lookup"><span data-stu-id="8514e-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8514e-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="8514e-116">**Media**</span></span> <br/> |<span data-ttu-id="8514e-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8514e-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8514e-118">Тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8514e-118">Media type.</span></span> <span data-ttu-id="8514e-119">Дополнительные сведения см. в таблице [MediaList.](medialist.md)</span><span class="sxs-lookup"><span data-stu-id="8514e-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8514e-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="8514e-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="8514e-121">datetime</span><span class="sxs-lookup"><span data-stu-id="8514e-121">datetime</span></span>  <br/> |<span data-ttu-id="8514e-122">Время отправки запроса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8514e-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="8514e-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="8514e-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="8514e-124">datetime</span><span class="sxs-lookup"><span data-stu-id="8514e-124">datetime</span></span>  <br/> |<span data-ttu-id="8514e-125">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="8514e-125">End time of the session.</span></span>  <br/> |
   

