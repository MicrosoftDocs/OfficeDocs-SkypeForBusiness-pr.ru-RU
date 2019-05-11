---
title: Таблица Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: В таблице диалогового окна представляет собой вспомогательную таблицу; Каждая запись представляет один диалоговое окно Session Initiation Protocol (SIP).
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920091"
---
# <a name="dialog-table"></a><span data-ttu-id="4c05d-103">Таблица Dialog</span><span class="sxs-lookup"><span data-stu-id="4c05d-103">Dialog table</span></span>
 
<span data-ttu-id="4c05d-104">В таблице диалогового окна представляет собой вспомогательную таблицу; Каждая запись представляет один диалоговое окно Session Initiation Protocol (SIP).</span><span class="sxs-lookup"><span data-stu-id="4c05d-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="4c05d-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4c05d-105">**Column**</span></span>|<span data-ttu-id="4c05d-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4c05d-106">**Data Type**</span></span>|<span data-ttu-id="4c05d-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4c05d-107">**Key/Index**</span></span>|<span data-ttu-id="4c05d-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4c05d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c05d-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="4c05d-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="4c05d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="4c05d-110">datetime</span></span>  <br/> |<span data-ttu-id="4c05d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4c05d-111">Primary</span></span>  <br/> |<span data-ttu-id="4c05d-112">Время, когда агент работы (QoE) получает первый отчет от вызывающего и вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4c05d-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="4c05d-113">Используется в сочетании с SessionSeq для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="4c05d-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="4c05d-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="4c05d-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="4c05d-115">целое</span><span class="sxs-lookup"><span data-stu-id="4c05d-115">int</span></span>  <br/> |<span data-ttu-id="4c05d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="4c05d-116">Primary</span></span>  <br/> |<span data-ttu-id="4c05d-117">Порядковый номер, позволяющий различать сеансы, когда у них есть же ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="4c05d-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="4c05d-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="4c05d-118">**DialogID**</span></span> <br/> |<span data-ttu-id="4c05d-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="4c05d-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="4c05d-120">Глобальный уникальный идентификатор диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="4c05d-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="4c05d-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="4c05d-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="4c05d-122">целое</span><span class="sxs-lookup"><span data-stu-id="4c05d-122">int</span></span>  <br/> |<span data-ttu-id="4c05d-123">Индекс</span><span class="sxs-lookup"><span data-stu-id="4c05d-123">index</span></span>  <br/> |<span data-ttu-id="4c05d-124">Контрольная сумма идентификатора диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="4c05d-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

