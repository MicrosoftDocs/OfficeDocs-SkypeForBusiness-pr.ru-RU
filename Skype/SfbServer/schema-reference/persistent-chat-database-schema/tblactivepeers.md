---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212679"
---
# <a name="tblactivepeers"></a><span data-ttu-id="f76b3-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="f76b3-103">tblActivePeers</span></span>
 
<span data-ttu-id="f76b3-104">Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="f76b3-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="f76b3-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f76b3-105">**Columns**</span></span>

|<span data-ttu-id="f76b3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f76b3-106">**Column**</span></span>|<span data-ttu-id="f76b3-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f76b3-107">**Type**</span></span>|<span data-ttu-id="f76b3-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f76b3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f76b3-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f76b3-109">aplServerID</span></span>  <br/> |<span data-ttu-id="f76b3-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="f76b3-110">int, not null</span></span>  <br/> |<span data-ttu-id="f76b3-111">Идентификатор сервера, добавившего запись.</span><span class="sxs-lookup"><span data-stu-id="f76b3-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="f76b3-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f76b3-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="f76b3-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="f76b3-113">int, not null</span></span>  <br/> |<span data-ttu-id="f76b3-114">ИД узла, который подключен сервер учета.</span><span class="sxs-lookup"><span data-stu-id="f76b3-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="f76b3-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="f76b3-115">**Keys**</span></span>

|<span data-ttu-id="f76b3-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f76b3-116">**Column**</span></span>|<span data-ttu-id="f76b3-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f76b3-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f76b3-118">\<aplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="f76b3-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="f76b3-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f76b3-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f76b3-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f76b3-120">aplServerID</span></span>  <br/> |<span data-ttu-id="f76b3-121">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="f76b3-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="f76b3-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f76b3-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="f76b3-123">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="f76b3-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

