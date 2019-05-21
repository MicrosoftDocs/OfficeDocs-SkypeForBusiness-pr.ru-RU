---
title: Таблица Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294959"
---
# <a name="dialog-table"></a><span data-ttu-id="07ea8-103">Таблица Dialog</span><span class="sxs-lookup"><span data-stu-id="07ea8-103">Dialog table</span></span>
 
<span data-ttu-id="07ea8-104">Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.</span><span class="sxs-lookup"><span data-stu-id="07ea8-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="07ea8-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="07ea8-105">**Column**</span></span>|<span data-ttu-id="07ea8-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="07ea8-106">**Data Type**</span></span>|<span data-ttu-id="07ea8-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="07ea8-107">**Key/Index**</span></span>|<span data-ttu-id="07ea8-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="07ea8-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07ea8-109">**Конференцедатетиме**</span><span class="sxs-lookup"><span data-stu-id="07ea8-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="07ea8-110">datetime</span><span class="sxs-lookup"><span data-stu-id="07ea8-110">datetime</span></span>  <br/> |<span data-ttu-id="07ea8-111">Primary</span><span class="sxs-lookup"><span data-stu-id="07ea8-111">Primary</span></span>  <br/> |<span data-ttu-id="07ea8-112">Время, когда агент качества (QoE) получает первый отчет от вызывающего или вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="07ea8-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="07ea8-113">Используется в сочетании с Сессионсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="07ea8-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="07ea8-114">**Сессионсек**</span><span class="sxs-lookup"><span data-stu-id="07ea8-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="07ea8-115">целое</span><span class="sxs-lookup"><span data-stu-id="07ea8-115">int</span></span>  <br/> |<span data-ttu-id="07ea8-116">Primary</span><span class="sxs-lookup"><span data-stu-id="07ea8-116">Primary</span></span>  <br/> |<span data-ttu-id="07ea8-117">Порядковый номер, чтобы отличать сеансы связи с одинаковым Конференцедатетиме.</span><span class="sxs-lookup"><span data-stu-id="07ea8-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="07ea8-118">**Диалогид**</span><span class="sxs-lookup"><span data-stu-id="07ea8-118">**DialogID**</span></span> <br/> |<span data-ttu-id="07ea8-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="07ea8-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="07ea8-120">ИДЕНТИФИКАТОР диалогового окна, который является глобально уникальным.</span><span class="sxs-lookup"><span data-stu-id="07ea8-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="07ea8-121">**Диалогидчекксум**</span><span class="sxs-lookup"><span data-stu-id="07ea8-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="07ea8-122">целое</span><span class="sxs-lookup"><span data-stu-id="07ea8-122">int</span></span>  <br/> |<span data-ttu-id="07ea8-123">индекса</span><span class="sxs-lookup"><span data-stu-id="07ea8-123">index</span></span>  <br/> |<span data-ttu-id="07ea8-124">Контрольная сумма идентификатора диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="07ea8-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

