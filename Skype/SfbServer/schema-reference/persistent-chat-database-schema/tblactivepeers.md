---
title: Таблица tblActivePeers
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
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a><span data-ttu-id="f0657-103">Таблица tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="f0657-103">tblActivePeers</span></span>
 
<span data-ttu-id="f0657-104">Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="f0657-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="f0657-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f0657-105">**Columns**</span></span>

|<span data-ttu-id="f0657-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f0657-106">**Column**</span></span>|<span data-ttu-id="f0657-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f0657-107">**Type**</span></span>|<span data-ttu-id="f0657-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f0657-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0657-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f0657-109">aplServerID</span></span>  <br/> |<span data-ttu-id="f0657-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="f0657-110">int, not null</span></span>  <br/> |<span data-ttu-id="f0657-111">Идентификатор сервера, добавившего запись.</span><span class="sxs-lookup"><span data-stu-id="f0657-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="f0657-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f0657-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="f0657-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="f0657-113">int, not null</span></span>  <br/> |<span data-ttu-id="f0657-114">ИД узла, который подключен сервер учета.</span><span class="sxs-lookup"><span data-stu-id="f0657-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="f0657-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="f0657-115">**Keys**</span></span>

|<span data-ttu-id="f0657-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f0657-116">**Column**</span></span>|<span data-ttu-id="f0657-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f0657-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0657-118">\<aplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="f0657-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="f0657-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f0657-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f0657-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f0657-120">aplServerID</span></span>  <br/> |<span data-ttu-id="f0657-121">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="f0657-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="f0657-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f0657-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="f0657-123">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="f0657-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

