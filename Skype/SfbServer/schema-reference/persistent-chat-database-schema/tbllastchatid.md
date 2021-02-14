---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816009"
---
# <a name="tbllastchatid"></a><span data-ttu-id="97e15-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="97e15-103">tblLastChatId</span></span>
 
<span data-ttu-id="97e15-104">Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="97e15-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="97e15-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="97e15-105">**Columns**</span></span>

|<span data-ttu-id="97e15-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="97e15-106">**Column**</span></span>|<span data-ttu-id="97e15-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="97e15-107">**Type**</span></span>|<span data-ttu-id="97e15-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="97e15-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97e15-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="97e15-109">nodeID</span></span>  <br/> |<span data-ttu-id="97e15-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="97e15-110">int, not null</span></span>  <br/> |<span data-ttu-id="97e15-111">Идентификатор узла (только типа комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="97e15-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="97e15-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="97e15-112">lastChatID</span></span>  <br/> |<span data-ttu-id="97e15-113">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="97e15-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="97e15-114">Идентификатор последнего чата.</span><span class="sxs-lookup"><span data-stu-id="97e15-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="97e15-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="97e15-115">**Keys**</span></span>

|<span data-ttu-id="97e15-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="97e15-116">**Column**</span></span>|<span data-ttu-id="97e15-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="97e15-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="97e15-118">Первичный ключ (для обработки достаточно nodeID).</span><span class="sxs-lookup"><span data-stu-id="97e15-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="97e15-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="97e15-119">nodeID</span></span>  <br/> |<span data-ttu-id="97e15-120">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="97e15-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="97e15-121">См. также</span><span class="sxs-lookup"><span data-stu-id="97e15-121">See also</span></span>

[<span data-ttu-id="97e15-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="97e15-122">tblChat</span></span>](tblchat.md)
