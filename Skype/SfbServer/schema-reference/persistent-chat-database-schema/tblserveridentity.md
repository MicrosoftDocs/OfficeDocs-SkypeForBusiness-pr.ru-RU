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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812277"
---
# <a name="tblserveridentity"></a><span data-ttu-id="b6b71-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="b6b71-103">tblServerIdentity</span></span>
 
<span data-ttu-id="b6b71-104">Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b6b71-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="b6b71-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="b6b71-105">**Columns**</span></span>

|<span data-ttu-id="b6b71-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b6b71-106">**Column**</span></span>|<span data-ttu-id="b6b71-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b6b71-107">**Type**</span></span>|<span data-ttu-id="b6b71-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b6b71-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6b71-109">серверид</span><span class="sxs-lookup"><span data-stu-id="b6b71-109">serverID</span></span>  <br/> |<span data-ttu-id="b6b71-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b6b71-110">int, not null</span></span>  <br/> |<span data-ttu-id="b6b71-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="b6b71-111">Server ID.</span></span> <span data-ttu-id="b6b71-112">Соответствует ИДЕНТИФИКАТОРу экземпляра из хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="b6b71-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="b6b71-113">сервераддресс</span><span class="sxs-lookup"><span data-stu-id="b6b71-113">serverAddress</span></span>  <br/> |<span data-ttu-id="b6b71-114">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b6b71-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b6b71-115">Адрес сервера с использованием адреса Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="b6b71-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="b6b71-116">серверластпингтиме</span><span class="sxs-lookup"><span data-stu-id="b6b71-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="b6b71-117">datetime</span><span class="sxs-lookup"><span data-stu-id="b6b71-117">datetime</span></span>  <br/> |<span data-ttu-id="b6b71-118">Последнее время, в течение которого сервер канала обновил эту строку, чтобы дать свидетельство о том, что оно запущено.</span><span class="sxs-lookup"><span data-stu-id="b6b71-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="b6b71-119">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="b6b71-119">**Key**</span></span>

|<span data-ttu-id="b6b71-120">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b6b71-120">**Column**</span></span>|<span data-ttu-id="b6b71-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b6b71-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6b71-122">серверид</span><span class="sxs-lookup"><span data-stu-id="b6b71-122">serverID</span></span>  <br/> |<span data-ttu-id="b6b71-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="b6b71-123">Primary key.</span></span>  <br/> |
   

