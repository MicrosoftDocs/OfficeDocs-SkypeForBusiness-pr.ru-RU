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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814587"
---
# <a name="tbllastchatid"></a><span data-ttu-id="6e256-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="6e256-103">tblLastChatId</span></span>
 
<span data-ttu-id="6e256-104">Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="6e256-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="6e256-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="6e256-105">**Columns**</span></span>

|<span data-ttu-id="6e256-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6e256-106">**Column**</span></span>|<span data-ttu-id="6e256-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6e256-107">**Type**</span></span>|<span data-ttu-id="6e256-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6e256-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e256-109">нодеид</span><span class="sxs-lookup"><span data-stu-id="6e256-109">nodeID</span></span>  <br/> |<span data-ttu-id="6e256-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6e256-110">int, not null</span></span>  <br/> |<span data-ttu-id="6e256-111">Идентификатор узла (комната чата — только тип).</span><span class="sxs-lookup"><span data-stu-id="6e256-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="6e256-112">ластчатид</span><span class="sxs-lookup"><span data-stu-id="6e256-112">lastChatID</span></span>  <br/> |<span data-ttu-id="6e256-113">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6e256-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="6e256-114">НОМЕР последнего использованного чата.</span><span class="sxs-lookup"><span data-stu-id="6e256-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="6e256-115">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="6e256-115">**Keys**</span></span>

|<span data-ttu-id="6e256-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6e256-116">**Column**</span></span>|<span data-ttu-id="6e256-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6e256-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e256-118">\<Нодеид, Ластчатид\></span><span class="sxs-lookup"><span data-stu-id="6e256-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="6e256-119">Первичный ключ (для обработки достаточно просто Нодеид).</span><span class="sxs-lookup"><span data-stu-id="6e256-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="6e256-120">нодеид</span><span class="sxs-lookup"><span data-stu-id="6e256-120">nodeID</span></span>  <br/> |<span data-ttu-id="6e256-121">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="6e256-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6e256-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6e256-122">See also</span></span>

[<span data-ttu-id="6e256-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="6e256-123">tblChat</span></span>](tblchat.md)
