---
title: Таблица IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920035"
---
# <a name="ipaddress-table"></a><span data-ttu-id="bd886-104">Таблица IPAddress</span><span class="sxs-lookup"><span data-stu-id="bd886-104">IPAddress table</span></span>
 
<span data-ttu-id="bd886-105">Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="bd886-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="bd886-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd886-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="bd886-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bd886-107">**Column**</span></span>|<span data-ttu-id="bd886-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bd886-108">**Data Type**</span></span>|<span data-ttu-id="bd886-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bd886-109">**Key/Index**</span></span>|<span data-ttu-id="bd886-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="bd886-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd886-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="bd886-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="bd886-112">целое</span><span class="sxs-lookup"><span data-stu-id="bd886-112">int</span></span>  <br/> |<span data-ttu-id="bd886-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bd886-113">Primary</span></span>  <br/> |<span data-ttu-id="bd886-114">Уникальный идентификатор для указанного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="bd886-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="bd886-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="bd886-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="bd886-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="bd886-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="bd886-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="bd886-117">Unique</span></span>  <br/> |<span data-ttu-id="bd886-118">Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="bd886-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="bd886-119">Это может быть IPv4 или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="bd886-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

