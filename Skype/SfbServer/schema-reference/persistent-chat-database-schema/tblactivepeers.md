---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295547"
---
# <a name="tblactivepeers"></a><span data-ttu-id="27b79-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="27b79-103">tblActivePeers</span></span>
 
<span data-ttu-id="27b79-104">Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="27b79-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="27b79-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="27b79-105">**Columns**</span></span>

|<span data-ttu-id="27b79-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="27b79-106">**Column**</span></span>|<span data-ttu-id="27b79-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="27b79-107">**Type**</span></span>|<span data-ttu-id="27b79-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="27b79-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="27b79-109">Аплсерверид</span><span class="sxs-lookup"><span data-stu-id="27b79-109">aplServerID</span></span>  <br/> |<span data-ttu-id="27b79-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="27b79-110">int, not null</span></span>  <br/> |<span data-ttu-id="27b79-111">Идентификатор сервера, на котором размещена запись.</span><span class="sxs-lookup"><span data-stu-id="27b79-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="27b79-112">Аплпирид</span><span class="sxs-lookup"><span data-stu-id="27b79-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="27b79-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="27b79-113">int, not null</span></span>  <br/> |<span data-ttu-id="27b79-114">Идентификатор однорангового узла, к которому подключен сервер публикации.</span><span class="sxs-lookup"><span data-stu-id="27b79-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="27b79-115">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="27b79-115">**Keys**</span></span>

|<span data-ttu-id="27b79-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="27b79-116">**Column**</span></span>|<span data-ttu-id="27b79-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="27b79-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="27b79-118">\<Аплсерверид, Аплпирид\></span><span class="sxs-lookup"><span data-stu-id="27b79-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="27b79-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="27b79-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="27b79-120">Аплсерверид</span><span class="sxs-lookup"><span data-stu-id="27b79-120">aplServerID</span></span>  <br/> |<span data-ttu-id="27b79-121">Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.</span><span class="sxs-lookup"><span data-stu-id="27b79-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="27b79-122">Аплпирид</span><span class="sxs-lookup"><span data-stu-id="27b79-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="27b79-123">Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.</span><span class="sxs-lookup"><span data-stu-id="27b79-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

