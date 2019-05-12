---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924810"
---
# <a name="tblserveridentity"></a><span data-ttu-id="331a4-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="331a4-103">tblServerIdentity</span></span>
 
<span data-ttu-id="331a4-104">tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="331a4-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="331a4-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="331a4-105">**Columns**</span></span>

|<span data-ttu-id="331a4-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="331a4-106">**Column**</span></span>|<span data-ttu-id="331a4-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="331a4-107">**Type**</span></span>|<span data-ttu-id="331a4-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="331a4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="331a4-109">Который</span><span class="sxs-lookup"><span data-stu-id="331a4-109">serverID</span></span>  <br/> |<span data-ttu-id="331a4-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="331a4-110">int, not null</span></span>  <br/> |<span data-ttu-id="331a4-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="331a4-111">Server ID.</span></span> <span data-ttu-id="331a4-112">Соответствует идентификатор экземпляра из хранилища централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="331a4-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="331a4-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="331a4-113">serverAddress</span></span>  <br/> |<span data-ttu-id="331a4-114">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="331a4-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="331a4-115">Адрес сервера с использованием адреса Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="331a4-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="331a4-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="331a4-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="331a4-117">datetime</span><span class="sxs-lookup"><span data-stu-id="331a4-117">datetime</span></span>  <br/> |<span data-ttu-id="331a4-118">Время последнего обновления этой строки для подтверждения функционирования сервером канала.</span><span class="sxs-lookup"><span data-stu-id="331a4-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="331a4-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="331a4-119">**Key**</span></span>

|<span data-ttu-id="331a4-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="331a4-120">**Column**</span></span>|<span data-ttu-id="331a4-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="331a4-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="331a4-122">Который</span><span class="sxs-lookup"><span data-stu-id="331a4-122">serverID</span></span>  <br/> |<span data-ttu-id="331a4-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="331a4-123">Primary key.</span></span>  <br/> |
   

