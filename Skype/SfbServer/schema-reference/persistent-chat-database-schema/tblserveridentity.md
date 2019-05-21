---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295190"
---
# <a name="tblserveridentity"></a><span data-ttu-id="155b8-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="155b8-103">tblServerIdentity</span></span>
 
<span data-ttu-id="155b8-104">Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="155b8-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="155b8-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="155b8-105">**Columns**</span></span>

|<span data-ttu-id="155b8-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="155b8-106">**Column**</span></span>|<span data-ttu-id="155b8-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="155b8-107">**Type**</span></span>|<span data-ttu-id="155b8-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="155b8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="155b8-109">Серверид</span><span class="sxs-lookup"><span data-stu-id="155b8-109">serverID</span></span>  <br/> |<span data-ttu-id="155b8-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="155b8-110">int, not null</span></span>  <br/> |<span data-ttu-id="155b8-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="155b8-111">Server ID.</span></span> <span data-ttu-id="155b8-112">Соответствует ИДЕНТИФИКАТОРу экземпляра из хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="155b8-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="155b8-113">Сервераддресс</span><span class="sxs-lookup"><span data-stu-id="155b8-113">serverAddress</span></span>  <br/> |<span data-ttu-id="155b8-114">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="155b8-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="155b8-115">Адрес сервера с использованием адреса Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="155b8-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="155b8-116">Серверластпингтиме</span><span class="sxs-lookup"><span data-stu-id="155b8-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="155b8-117">datetime</span><span class="sxs-lookup"><span data-stu-id="155b8-117">datetime</span></span>  <br/> |<span data-ttu-id="155b8-118">Последнее время, в течение которого сервер канала обновил эту строку, чтобы дать свидетельство о том, что оно запущено.</span><span class="sxs-lookup"><span data-stu-id="155b8-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="155b8-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="155b8-119">**Key**</span></span>

|<span data-ttu-id="155b8-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="155b8-120">**Column**</span></span>|<span data-ttu-id="155b8-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="155b8-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="155b8-122">Серверид</span><span class="sxs-lookup"><span data-stu-id="155b8-122">serverID</span></span>  <br/> |<span data-ttu-id="155b8-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="155b8-123">Primary key.</span></span>  <br/> |
   

