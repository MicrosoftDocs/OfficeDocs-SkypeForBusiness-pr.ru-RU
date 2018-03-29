---
title: tblServerIdentity
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
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a><span data-ttu-id="f6bd6-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="f6bd6-103">tblServerIdentity</span></span>
 
<span data-ttu-id="f6bd6-104">tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f6bd6-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="f6bd6-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f6bd6-105">**Columns**</span></span>

|<span data-ttu-id="f6bd6-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f6bd6-106">**Column**</span></span>|<span data-ttu-id="f6bd6-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f6bd6-107">**Type**</span></span>|<span data-ttu-id="f6bd6-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6bd6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6bd6-109">Который</span><span class="sxs-lookup"><span data-stu-id="f6bd6-109">serverID</span></span>  <br/> |<span data-ttu-id="f6bd6-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="f6bd6-110">int, not null</span></span>  <br/> |<span data-ttu-id="f6bd6-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="f6bd6-111">Server ID.</span></span> <span data-ttu-id="f6bd6-112">Соответствует идентификатор экземпляра из хранилища централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="f6bd6-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="f6bd6-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="f6bd6-113">serverAddress</span></span>  <br/> |<span data-ttu-id="f6bd6-114">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="f6bd6-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f6bd6-115">Адрес сервера с использованием адреса Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="f6bd6-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="f6bd6-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="f6bd6-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="f6bd6-117">datetime</span><span class="sxs-lookup"><span data-stu-id="f6bd6-117">datetime</span></span>  <br/> |<span data-ttu-id="f6bd6-118">Время последнего обновления этой строки для подтверждения функционирования сервером канала.</span><span class="sxs-lookup"><span data-stu-id="f6bd6-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="f6bd6-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="f6bd6-119">**Key**</span></span>

|<span data-ttu-id="f6bd6-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f6bd6-120">**Column**</span></span>|<span data-ttu-id="f6bd6-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6bd6-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6bd6-122">Который</span><span class="sxs-lookup"><span data-stu-id="f6bd6-122">serverID</span></span>  <br/> |<span data-ttu-id="f6bd6-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f6bd6-123">Primary key.</span></span>  <br/> |
   

