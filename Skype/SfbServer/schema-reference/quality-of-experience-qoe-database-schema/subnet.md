---
title: Таблица Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831339"
---
# <a name="subnet-table"></a><span data-ttu-id="f134b-104">Таблица Subnet</span><span class="sxs-lookup"><span data-stu-id="f134b-104">Subnet table</span></span>
 
<span data-ttu-id="f134b-p102">Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="f134b-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="f134b-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f134b-107">**Column**</span></span>|<span data-ttu-id="f134b-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="f134b-108">**Data Type**</span></span>|<span data-ttu-id="f134b-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="f134b-109">**Key/Index**</span></span>|<span data-ttu-id="f134b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f134b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f134b-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="f134b-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="f134b-112">int</span><span class="sxs-lookup"><span data-stu-id="f134b-112">int</span></span>  <br/> |<span data-ttu-id="f134b-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="f134b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f134b-114">Целочисленное представление IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="f134b-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="f134b-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="f134b-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="f134b-116">int</span><span class="sxs-lookup"><span data-stu-id="f134b-116">int</span></span>  <br/> ||<span data-ttu-id="f134b-117">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="f134b-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="f134b-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="f134b-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="f134b-119">int</span><span class="sxs-lookup"><span data-stu-id="f134b-119">int</span></span>  <br/> |<span data-ttu-id="f134b-120">Внешняя</span><span class="sxs-lookup"><span data-stu-id="f134b-120">Foreign</span></span>  <br/> |<span data-ttu-id="f134b-121">Ссылка из [таблицы UserSite.](usersite.md)</span><span class="sxs-lookup"><span data-stu-id="f134b-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="f134b-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="f134b-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="f134b-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="f134b-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="f134b-124">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="f134b-124">The description for the subnet.</span></span>  <br/> |
   

