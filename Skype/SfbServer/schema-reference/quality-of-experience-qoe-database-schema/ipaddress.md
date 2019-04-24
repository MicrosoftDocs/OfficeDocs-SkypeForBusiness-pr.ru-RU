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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212209"
---
# <a name="ipaddress-table"></a><span data-ttu-id="ecf00-104">Таблица IPAddress</span><span class="sxs-lookup"><span data-stu-id="ecf00-104">IPAddress table</span></span>
 
<span data-ttu-id="ecf00-105">Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ecf00-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="ecf00-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecf00-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ecf00-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ecf00-107">**Column**</span></span>|<span data-ttu-id="ecf00-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ecf00-108">**Data Type**</span></span>|<span data-ttu-id="ecf00-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ecf00-109">**Key/Index**</span></span>|<span data-ttu-id="ecf00-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ecf00-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ecf00-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="ecf00-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="ecf00-112">целое</span><span class="sxs-lookup"><span data-stu-id="ecf00-112">int</span></span>  <br/> |<span data-ttu-id="ecf00-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ecf00-113">Primary</span></span>  <br/> |<span data-ttu-id="ecf00-114">Уникальный идентификатор для указанного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="ecf00-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="ecf00-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="ecf00-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="ecf00-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="ecf00-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="ecf00-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="ecf00-117">Unique</span></span>  <br/> |<span data-ttu-id="ecf00-118">Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="ecf00-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="ecf00-119">Это может быть IPv4 или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="ecf00-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

