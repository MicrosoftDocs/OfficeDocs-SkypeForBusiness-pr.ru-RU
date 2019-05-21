---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295400"
---
# <a name="tbllastchatid"></a><span data-ttu-id="85ac8-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="85ac8-103">tblLastChatId</span></span>
 
<span data-ttu-id="85ac8-104">Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="85ac8-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="85ac8-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="85ac8-105">**Columns**</span></span>

|<span data-ttu-id="85ac8-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="85ac8-106">**Column**</span></span>|<span data-ttu-id="85ac8-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="85ac8-107">**Type**</span></span>|<span data-ttu-id="85ac8-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="85ac8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85ac8-109">Нодеид</span><span class="sxs-lookup"><span data-stu-id="85ac8-109">nodeID</span></span>  <br/> |<span data-ttu-id="85ac8-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="85ac8-110">int, not null</span></span>  <br/> |<span data-ttu-id="85ac8-111">Идентификатор узла (комната чата — только тип).</span><span class="sxs-lookup"><span data-stu-id="85ac8-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="85ac8-112">Ластчатид</span><span class="sxs-lookup"><span data-stu-id="85ac8-112">lastChatID</span></span>  <br/> |<span data-ttu-id="85ac8-113">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="85ac8-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="85ac8-114">НОМЕР последнего использованного чата.</span><span class="sxs-lookup"><span data-stu-id="85ac8-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="85ac8-115">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="85ac8-115">**Keys**</span></span>

|<span data-ttu-id="85ac8-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="85ac8-116">**Column**</span></span>|<span data-ttu-id="85ac8-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="85ac8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85ac8-118">\<Нодеид, Ластчатид\></span><span class="sxs-lookup"><span data-stu-id="85ac8-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="85ac8-119">Первичный ключ (для обработки достаточно просто Нодеид).</span><span class="sxs-lookup"><span data-stu-id="85ac8-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="85ac8-120">Нодеид</span><span class="sxs-lookup"><span data-stu-id="85ac8-120">nodeID</span></span>  <br/> |<span data-ttu-id="85ac8-121">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="85ac8-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="85ac8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="85ac8-122">See also</span></span>

[<span data-ttu-id="85ac8-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="85ac8-123">tblChat</span></span>](tblchat.md)
