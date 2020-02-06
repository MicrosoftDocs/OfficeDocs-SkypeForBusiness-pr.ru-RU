---
title: Таблица IP-адреса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: В таблице IPAddress IP-адреса сопоставляются с уникальными идентификаторами IP-адресов, которые используются в базе данных качества обслуживания. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809547"
---
# <a name="ipaddress-table"></a><span data-ttu-id="e990f-104">Таблица IP-адреса</span><span class="sxs-lookup"><span data-stu-id="e990f-104">IPAddress table</span></span>
 
<span data-ttu-id="e990f-105">В таблице IPAddress IP-адреса сопоставляются с уникальными идентификаторами IP-адресов, которые используются в базе данных качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e990f-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="e990f-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e990f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e990f-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e990f-107">**Column**</span></span>|<span data-ttu-id="e990f-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e990f-108">**Data Type**</span></span>|<span data-ttu-id="e990f-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="e990f-109">**Key/Index**</span></span>|<span data-ttu-id="e990f-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e990f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e990f-111">**ипаддресскэй**</span><span class="sxs-lookup"><span data-stu-id="e990f-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="e990f-112">целое</span><span class="sxs-lookup"><span data-stu-id="e990f-112">int</span></span>  <br/> |<span data-ttu-id="e990f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e990f-113">Primary</span></span>  <br/> |<span data-ttu-id="e990f-114">Уникальный идентификатор указанного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="e990f-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="e990f-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="e990f-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="e990f-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="e990f-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="e990f-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="e990f-117">Unique</span></span>  <br/> |<span data-ttu-id="e990f-118">Уникальный IP-адрес (например, 189.168.1.1), сопоставляемый с Ипаддресскэй.</span><span class="sxs-lookup"><span data-stu-id="e990f-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="e990f-119">Это может быть либо IPv4, либо IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="e990f-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

