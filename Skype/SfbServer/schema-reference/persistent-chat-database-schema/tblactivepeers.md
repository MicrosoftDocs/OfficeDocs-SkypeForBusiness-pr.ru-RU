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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814717"
---
# <a name="tblactivepeers"></a><span data-ttu-id="0aa54-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="0aa54-103">tblActivePeers</span></span>
 
<span data-ttu-id="0aa54-104">Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="0aa54-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="0aa54-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="0aa54-105">**Columns**</span></span>

|<span data-ttu-id="0aa54-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0aa54-106">**Column**</span></span>|<span data-ttu-id="0aa54-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0aa54-107">**Type**</span></span>|<span data-ttu-id="0aa54-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0aa54-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0aa54-109">аплсерверид</span><span class="sxs-lookup"><span data-stu-id="0aa54-109">aplServerID</span></span>  <br/> |<span data-ttu-id="0aa54-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0aa54-110">int, not null</span></span>  <br/> |<span data-ttu-id="0aa54-111">Идентификатор сервера, на котором размещена запись.</span><span class="sxs-lookup"><span data-stu-id="0aa54-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="0aa54-112">аплпирид</span><span class="sxs-lookup"><span data-stu-id="0aa54-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="0aa54-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0aa54-113">int, not null</span></span>  <br/> |<span data-ttu-id="0aa54-114">Идентификатор однорангового узла, к которому подключен сервер публикации.</span><span class="sxs-lookup"><span data-stu-id="0aa54-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="0aa54-115">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="0aa54-115">**Keys**</span></span>

|<span data-ttu-id="0aa54-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0aa54-116">**Column**</span></span>|<span data-ttu-id="0aa54-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0aa54-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0aa54-118">\<Аплсерверид, Аплпирид\></span><span class="sxs-lookup"><span data-stu-id="0aa54-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="0aa54-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="0aa54-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0aa54-120">аплсерверид</span><span class="sxs-lookup"><span data-stu-id="0aa54-120">aplServerID</span></span>  <br/> |<span data-ttu-id="0aa54-121">Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.</span><span class="sxs-lookup"><span data-stu-id="0aa54-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="0aa54-122">аплпирид</span><span class="sxs-lookup"><span data-stu-id="0aa54-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="0aa54-123">Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.</span><span class="sxs-lookup"><span data-stu-id="0aa54-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

