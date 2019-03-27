---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899528"
---
# <a name="tblserveridentity"></a><span data-ttu-id="2a746-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="2a746-103">tblServerIdentity</span></span>
 
<span data-ttu-id="2a746-104">tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="2a746-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="2a746-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="2a746-105">**Columns**</span></span>

|<span data-ttu-id="2a746-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a746-106">**Column**</span></span>|<span data-ttu-id="2a746-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2a746-107">**Type**</span></span>|<span data-ttu-id="2a746-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="2a746-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a746-109">Который</span><span class="sxs-lookup"><span data-stu-id="2a746-109">serverID</span></span>  <br/> |<span data-ttu-id="2a746-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="2a746-110">int, not null</span></span>  <br/> |<span data-ttu-id="2a746-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="2a746-111">Server ID.</span></span> <span data-ttu-id="2a746-112">Соответствует идентификатор экземпляра из хранилища централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="2a746-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="2a746-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="2a746-113">serverAddress</span></span>  <br/> |<span data-ttu-id="2a746-114">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="2a746-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2a746-115">Адрес сервера с использованием адреса Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="2a746-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="2a746-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="2a746-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="2a746-117">datetime</span><span class="sxs-lookup"><span data-stu-id="2a746-117">datetime</span></span>  <br/> |<span data-ttu-id="2a746-118">Время последнего обновления этой строки для подтверждения функционирования сервером канала.</span><span class="sxs-lookup"><span data-stu-id="2a746-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="2a746-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="2a746-119">**Key**</span></span>

|<span data-ttu-id="2a746-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a746-120">**Column**</span></span>|<span data-ttu-id="2a746-121">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="2a746-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a746-122">Который</span><span class="sxs-lookup"><span data-stu-id="2a746-122">serverID</span></span>  <br/> |<span data-ttu-id="2a746-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="2a746-123">Primary key.</span></span>  <br/> |
   

