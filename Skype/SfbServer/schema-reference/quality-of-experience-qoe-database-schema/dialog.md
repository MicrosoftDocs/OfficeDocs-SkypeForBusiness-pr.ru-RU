---
title: Таблица Dialog
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815849"
---
# <a name="dialog-table"></a><span data-ttu-id="2ddad-103">Таблица Dialog</span><span class="sxs-lookup"><span data-stu-id="2ddad-103">Dialog table</span></span>
 
<span data-ttu-id="2ddad-104">Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.</span><span class="sxs-lookup"><span data-stu-id="2ddad-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="2ddad-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2ddad-105">**Column**</span></span>|<span data-ttu-id="2ddad-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2ddad-106">**Data Type**</span></span>|<span data-ttu-id="2ddad-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="2ddad-107">**Key/Index**</span></span>|<span data-ttu-id="2ddad-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="2ddad-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ddad-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="2ddad-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="2ddad-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2ddad-110">datetime</span></span>  <br/> |<span data-ttu-id="2ddad-111">Primary</span><span class="sxs-lookup"><span data-stu-id="2ddad-111">Primary</span></span>  <br/> |<span data-ttu-id="2ddad-p101">Время получения  агентом качества обслуживания первого отчета от звонящего или вызываемого абонента. Используется совместно с SessionSeq для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="2ddad-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2ddad-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="2ddad-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="2ddad-115">int</span><span class="sxs-lookup"><span data-stu-id="2ddad-115">int</span></span>  <br/> |<span data-ttu-id="2ddad-116">Primary</span><span class="sxs-lookup"><span data-stu-id="2ddad-116">Primary</span></span>  <br/> |<span data-ttu-id="2ddad-117">Порядковый номер, позволяющий различать сеансы с одинаковым ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="2ddad-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="2ddad-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="2ddad-118">**DialogID**</span></span> <br/> |<span data-ttu-id="2ddad-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ddad-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="2ddad-120">Глобальный уникальный идентификатор диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="2ddad-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="2ddad-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="2ddad-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="2ddad-122">int</span><span class="sxs-lookup"><span data-stu-id="2ddad-122">int</span></span>  <br/> |<span data-ttu-id="2ddad-123">index</span><span class="sxs-lookup"><span data-stu-id="2ddad-123">index</span></span>  <br/> |<span data-ttu-id="2ddad-124">Контрольная сумма идентификатора диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="2ddad-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

