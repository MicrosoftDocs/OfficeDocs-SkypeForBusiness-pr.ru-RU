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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884169"
---
# <a name="tblactivepeers"></a><span data-ttu-id="696e9-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="696e9-103">tblActivePeers</span></span>
 
<span data-ttu-id="696e9-104">Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="696e9-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="696e9-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="696e9-105">**Columns**</span></span>

|<span data-ttu-id="696e9-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="696e9-106">**Column**</span></span>|<span data-ttu-id="696e9-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="696e9-107">**Type**</span></span>|<span data-ttu-id="696e9-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="696e9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="696e9-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="696e9-109">aplServerID</span></span>  <br/> |<span data-ttu-id="696e9-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="696e9-110">int, not null</span></span>  <br/> |<span data-ttu-id="696e9-111">Идентификатор сервера, добавившего запись.</span><span class="sxs-lookup"><span data-stu-id="696e9-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="696e9-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="696e9-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="696e9-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="696e9-113">int, not null</span></span>  <br/> |<span data-ttu-id="696e9-114">ИД узла, который подключен сервер учета.</span><span class="sxs-lookup"><span data-stu-id="696e9-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="696e9-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="696e9-115">**Keys**</span></span>

|<span data-ttu-id="696e9-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="696e9-116">**Column**</span></span>|<span data-ttu-id="696e9-117">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="696e9-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="696e9-118">\<aplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="696e9-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="696e9-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="696e9-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="696e9-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="696e9-120">aplServerID</span></span>  <br/> |<span data-ttu-id="696e9-121">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="696e9-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="696e9-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="696e9-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="696e9-123">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="696e9-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

