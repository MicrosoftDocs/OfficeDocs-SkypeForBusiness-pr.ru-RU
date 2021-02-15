---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity содержит активные серверы чата в пуле серверов сохраняемого чата.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831499"
---
# <a name="tblserveridentity"></a><span data-ttu-id="e5544-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="e5544-103">tblServerIdentity</span></span>
 
<span data-ttu-id="e5544-104">tblServerIdentity содержит активные серверы чата в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="e5544-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="e5544-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e5544-105">**Columns**</span></span>

|<span data-ttu-id="e5544-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e5544-106">**Column**</span></span>|<span data-ttu-id="e5544-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e5544-107">**Type**</span></span>|<span data-ttu-id="e5544-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e5544-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5544-109">serverID</span><span class="sxs-lookup"><span data-stu-id="e5544-109">serverID</span></span>  <br/> |<span data-ttu-id="e5544-110">целое, не равно null</span><span class="sxs-lookup"><span data-stu-id="e5544-110">int, not null</span></span>  <br/> |<span data-ttu-id="e5544-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="e5544-111">Server ID.</span></span> <span data-ttu-id="e5544-112">Соответствует ИД экземпляра из центрального банка управления.</span><span class="sxs-lookup"><span data-stu-id="e5544-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="e5544-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="e5544-113">serverAddress</span></span>  <br/> |<span data-ttu-id="e5544-114">nvarchar (256), не равно null</span><span class="sxs-lookup"><span data-stu-id="e5544-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e5544-115">Адрес сервера с использованием адреса платформы Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="e5544-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="e5544-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="e5544-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="e5544-117">datetime</span><span class="sxs-lookup"><span data-stu-id="e5544-117">datetime</span></span>  <br/> |<span data-ttu-id="e5544-118">Время последнего обновления этой строки сервером канала для подтверждения функционирования.</span><span class="sxs-lookup"><span data-stu-id="e5544-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="e5544-119">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="e5544-119">**Key**</span></span>

|<span data-ttu-id="e5544-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e5544-120">**Column**</span></span>|<span data-ttu-id="e5544-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e5544-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5544-122">serverID</span><span class="sxs-lookup"><span data-stu-id="e5544-122">serverID</span></span>  <br/> |<span data-ttu-id="e5544-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e5544-123">Primary key.</span></span>  <br/> |
   

