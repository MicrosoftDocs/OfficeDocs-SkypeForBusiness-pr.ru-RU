---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Таблица tblLastChatId содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.
ms.openlocfilehash: 9d19c6c873660683ff526eb144d74b6e8752bf80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929968"
---
# <a name="tbllastchatid"></a><span data-ttu-id="5f89f-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="5f89f-103">tblLastChatId</span></span>
 
<span data-ttu-id="5f89f-104">Таблица tblLastChatId содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5f89f-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="5f89f-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="5f89f-105">**Columns**</span></span>

|<span data-ttu-id="5f89f-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5f89f-106">**Column**</span></span>|<span data-ttu-id="5f89f-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5f89f-107">**Type**</span></span>|<span data-ttu-id="5f89f-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5f89f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f89f-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="5f89f-109">nodeID</span></span>  <br/> |<span data-ttu-id="5f89f-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="5f89f-110">int, not null</span></span>  <br/> |<span data-ttu-id="5f89f-111">КОД узла (только типа комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="5f89f-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="5f89f-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="5f89f-112">lastChatID</span></span>  <br/> |<span data-ttu-id="5f89f-113">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5f89f-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="5f89f-114">Последний идентификатор чата.</span><span class="sxs-lookup"><span data-stu-id="5f89f-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="5f89f-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="5f89f-115">**Keys**</span></span>

|<span data-ttu-id="5f89f-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5f89f-116">**Column**</span></span>|<span data-ttu-id="5f89f-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5f89f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f89f-118">\<nodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="5f89f-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="5f89f-119">Первичный ключ (достаточно NodeId для обработки).</span><span class="sxs-lookup"><span data-stu-id="5f89f-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="5f89f-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="5f89f-120">nodeID</span></span>  <br/> |<span data-ttu-id="5f89f-121">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="5f89f-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5f89f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5f89f-122">See also</span></span>

[<span data-ttu-id="5f89f-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="5f89f-123">tblChat</span></span>](tblchat.md)
