---
title: Таблица IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876960"
---
# <a name="ipaddress-table"></a><span data-ttu-id="e96da-104">Таблица IPAddress</span><span class="sxs-lookup"><span data-stu-id="e96da-104">IPAddress table</span></span>
 
<span data-ttu-id="e96da-105">Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e96da-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="e96da-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e96da-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e96da-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e96da-107">**Column**</span></span>|<span data-ttu-id="e96da-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e96da-108">**Data Type**</span></span>|<span data-ttu-id="e96da-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="e96da-109">**Key/Index**</span></span>|<span data-ttu-id="e96da-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e96da-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e96da-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="e96da-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="e96da-112">целое</span><span class="sxs-lookup"><span data-stu-id="e96da-112">int</span></span>  <br/> |<span data-ttu-id="e96da-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e96da-113">Primary</span></span>  <br/> |<span data-ttu-id="e96da-114">Уникальный идентификатор для указанного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="e96da-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="e96da-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="e96da-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="e96da-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="e96da-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="e96da-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="e96da-117">Unique</span></span>  <br/> |<span data-ttu-id="e96da-118">Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="e96da-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="e96da-119">Это может быть IPv4 или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="e96da-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

