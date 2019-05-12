---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929877"
---
# <a name="tblactivepeers"></a><span data-ttu-id="94afb-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="94afb-103">tblActivePeers</span></span>
 
<span data-ttu-id="94afb-104">Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="94afb-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="94afb-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="94afb-105">**Columns**</span></span>

|<span data-ttu-id="94afb-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="94afb-106">**Column**</span></span>|<span data-ttu-id="94afb-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="94afb-107">**Type**</span></span>|<span data-ttu-id="94afb-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="94afb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94afb-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="94afb-109">aplServerID</span></span>  <br/> |<span data-ttu-id="94afb-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="94afb-110">int, not null</span></span>  <br/> |<span data-ttu-id="94afb-111">Идентификатор сервера, добавившего запись.</span><span class="sxs-lookup"><span data-stu-id="94afb-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="94afb-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="94afb-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="94afb-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="94afb-113">int, not null</span></span>  <br/> |<span data-ttu-id="94afb-114">ИД узла, который подключен сервер учета.</span><span class="sxs-lookup"><span data-stu-id="94afb-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="94afb-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="94afb-115">**Keys**</span></span>

|<span data-ttu-id="94afb-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="94afb-116">**Column**</span></span>|<span data-ttu-id="94afb-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="94afb-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="94afb-118">\<aplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="94afb-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="94afb-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="94afb-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="94afb-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="94afb-120">aplServerID</span></span>  <br/> |<span data-ttu-id="94afb-121">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="94afb-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="94afb-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="94afb-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="94afb-123">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="94afb-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

