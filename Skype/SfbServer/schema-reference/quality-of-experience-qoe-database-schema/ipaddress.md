---
title: Таблица IPAddress
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Таблица IPAddress сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, которые используются в других местах базы данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802779"
---
# <a name="ipaddress-table"></a><span data-ttu-id="ecd07-104">Таблица IPAddress</span><span class="sxs-lookup"><span data-stu-id="ecd07-104">IPAddress table</span></span>
 
<span data-ttu-id="ecd07-105">Таблица IPAddress сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, которые используются в других местах базы данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ecd07-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="ecd07-106">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecd07-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ecd07-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ecd07-107">**Column**</span></span>|<span data-ttu-id="ecd07-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ecd07-108">**Data Type**</span></span>|<span data-ttu-id="ecd07-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ecd07-109">**Key/Index**</span></span>|<span data-ttu-id="ecd07-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ecd07-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ecd07-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="ecd07-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="ecd07-112">int</span><span class="sxs-lookup"><span data-stu-id="ecd07-112">int</span></span>  <br/> |<span data-ttu-id="ecd07-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ecd07-113">Primary</span></span>  <br/> |<span data-ttu-id="ecd07-114">Уникальный идентификатор указанного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="ecd07-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="ecd07-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="ecd07-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="ecd07-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="ecd07-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="ecd07-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="ecd07-117">Unique</span></span>  <br/> |<span data-ttu-id="ecd07-p103">Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IPAddressKey. Адрес может быть представлен в формате IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="ecd07-p103">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

