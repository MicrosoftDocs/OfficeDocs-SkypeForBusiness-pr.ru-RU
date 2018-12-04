---
title: tblLastChatId
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
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505092"
---
# <a name="tbllastchatid"></a><span data-ttu-id="8d4d5-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="8d4d5-103">tblLastChatId</span></span>
 
<span data-ttu-id="8d4d5-104">Таблица tblLastChatId содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d4d5-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="8d4d5-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="8d4d5-105">**Columns**</span></span>

|<span data-ttu-id="8d4d5-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8d4d5-106">**Column**</span></span>|<span data-ttu-id="8d4d5-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8d4d5-107">**Type**</span></span>|<span data-ttu-id="8d4d5-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8d4d5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8d4d5-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="8d4d5-109">nodeID</span></span>  <br/> |<span data-ttu-id="8d4d5-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="8d4d5-110">int, not null</span></span>  <br/> |<span data-ttu-id="8d4d5-111">КОД узла (только типа комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="8d4d5-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="8d4d5-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="8d4d5-112">lastChatID</span></span>  <br/> |<span data-ttu-id="8d4d5-113">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="8d4d5-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="8d4d5-114">Последний идентификатор чата.</span><span class="sxs-lookup"><span data-stu-id="8d4d5-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="8d4d5-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="8d4d5-115">**Keys**</span></span>

|<span data-ttu-id="8d4d5-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8d4d5-116">**Column**</span></span>|<span data-ttu-id="8d4d5-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8d4d5-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d4d5-118">\<nodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="8d4d5-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="8d4d5-119">Первичный ключ (достаточно NodeId для обработки).</span><span class="sxs-lookup"><span data-stu-id="8d4d5-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="8d4d5-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="8d4d5-120">nodeID</span></span>  <br/> |<span data-ttu-id="8d4d5-121">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="8d4d5-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8d4d5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8d4d5-122">See also</span></span>

[<span data-ttu-id="8d4d5-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="8d4d5-123">tblChat</span></span>](tblchat.md)