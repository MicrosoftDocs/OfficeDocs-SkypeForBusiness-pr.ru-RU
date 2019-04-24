---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Таблица tblLastChatId содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212567"
---
# <a name="tbllastchatid"></a><span data-ttu-id="ebc59-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="ebc59-103">tblLastChatId</span></span>
 
<span data-ttu-id="ebc59-104">Таблица tblLastChatId содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ebc59-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="ebc59-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="ebc59-105">**Columns**</span></span>

|<span data-ttu-id="ebc59-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ebc59-106">**Column**</span></span>|<span data-ttu-id="ebc59-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ebc59-107">**Type**</span></span>|<span data-ttu-id="ebc59-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ebc59-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ebc59-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="ebc59-109">nodeID</span></span>  <br/> |<span data-ttu-id="ebc59-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="ebc59-110">int, not null</span></span>  <br/> |<span data-ttu-id="ebc59-111">КОД узла (только типа комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="ebc59-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="ebc59-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="ebc59-112">lastChatID</span></span>  <br/> |<span data-ttu-id="ebc59-113">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="ebc59-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="ebc59-114">Последний идентификатор чата.</span><span class="sxs-lookup"><span data-stu-id="ebc59-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="ebc59-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="ebc59-115">**Keys**</span></span>

|<span data-ttu-id="ebc59-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ebc59-116">**Column**</span></span>|<span data-ttu-id="ebc59-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ebc59-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ebc59-118">\<nodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="ebc59-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="ebc59-119">Первичный ключ (достаточно NodeId для обработки).</span><span class="sxs-lookup"><span data-stu-id="ebc59-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="ebc59-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="ebc59-120">nodeID</span></span>  <br/> |<span data-ttu-id="ebc59-121">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="ebc59-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ebc59-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ebc59-122">See also</span></span>

[<span data-ttu-id="ebc59-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="ebc59-123">tblChat</span></span>](tblchat.md)
