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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809537"
---
# <a name="dialog-table"></a><span data-ttu-id="01e6b-103">Таблица Dialog</span><span class="sxs-lookup"><span data-stu-id="01e6b-103">Dialog table</span></span>
 
<span data-ttu-id="01e6b-104">Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.</span><span class="sxs-lookup"><span data-stu-id="01e6b-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="01e6b-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="01e6b-105">**Column**</span></span>|<span data-ttu-id="01e6b-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="01e6b-106">**Data Type**</span></span>|<span data-ttu-id="01e6b-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="01e6b-107">**Key/Index**</span></span>|<span data-ttu-id="01e6b-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="01e6b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01e6b-109">**конференцедатетиме**</span><span class="sxs-lookup"><span data-stu-id="01e6b-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="01e6b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="01e6b-110">datetime</span></span>  <br/> |<span data-ttu-id="01e6b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="01e6b-111">Primary</span></span>  <br/> |<span data-ttu-id="01e6b-112">Время, когда агент качества (QoE) получает первый отчет от вызывающего или вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="01e6b-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="01e6b-113">Используется в сочетании с Сессионсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="01e6b-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="01e6b-114">**сессионсек**</span><span class="sxs-lookup"><span data-stu-id="01e6b-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="01e6b-115">целое</span><span class="sxs-lookup"><span data-stu-id="01e6b-115">int</span></span>  <br/> |<span data-ttu-id="01e6b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="01e6b-116">Primary</span></span>  <br/> |<span data-ttu-id="01e6b-117">Порядковый номер, чтобы отличать сеансы связи с одинаковым Конференцедатетиме.</span><span class="sxs-lookup"><span data-stu-id="01e6b-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="01e6b-118">**диалогид**</span><span class="sxs-lookup"><span data-stu-id="01e6b-118">**DialogID**</span></span> <br/> |<span data-ttu-id="01e6b-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="01e6b-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="01e6b-120">ИДЕНТИФИКАТОР диалогового окна, который является глобально уникальным.</span><span class="sxs-lookup"><span data-stu-id="01e6b-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="01e6b-121">**диалогидчекксум**</span><span class="sxs-lookup"><span data-stu-id="01e6b-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="01e6b-122">целое</span><span class="sxs-lookup"><span data-stu-id="01e6b-122">int</span></span>  <br/> |<span data-ttu-id="01e6b-123">индекса</span><span class="sxs-lookup"><span data-stu-id="01e6b-123">index</span></span>  <br/> |<span data-ttu-id="01e6b-124">Контрольная сумма идентификатора диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="01e6b-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

