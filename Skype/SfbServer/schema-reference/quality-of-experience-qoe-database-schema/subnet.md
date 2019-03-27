---
title: Таблица Subnet
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица Subnet представляет собой вспомогательную таблицу. Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880478"
---
# <a name="subnet-table"></a><span data-ttu-id="b0734-104">Таблица Subnet</span><span class="sxs-lookup"><span data-stu-id="b0734-104">Subnet table</span></span>
 
<span data-ttu-id="b0734-105">Таблица Subnet представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="b0734-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="b0734-106">Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="b0734-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="b0734-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b0734-107">**Column**</span></span>|<span data-ttu-id="b0734-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b0734-108">**Data Type**</span></span>|<span data-ttu-id="b0734-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="b0734-109">**Key/Index**</span></span>|<span data-ttu-id="b0734-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="b0734-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b0734-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="b0734-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="b0734-112">целое</span><span class="sxs-lookup"><span data-stu-id="b0734-112">int</span></span>  <br/> |<span data-ttu-id="b0734-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="b0734-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b0734-114">Целое число, представляющее IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="b0734-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="b0734-115">**Маска подсети**</span><span class="sxs-lookup"><span data-stu-id="b0734-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="b0734-116">целое</span><span class="sxs-lookup"><span data-stu-id="b0734-116">int</span></span>  <br/> ||<span data-ttu-id="b0734-117">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="b0734-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="b0734-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="b0734-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="b0734-119">целое</span><span class="sxs-lookup"><span data-stu-id="b0734-119">int</span></span>  <br/> |<span data-ttu-id="b0734-120">Внешний</span><span class="sxs-lookup"><span data-stu-id="b0734-120">Foreign</span></span>  <br/> |<span data-ttu-id="b0734-121">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="b0734-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="b0734-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="b0734-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="b0734-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="b0734-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="b0734-124">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="b0734-124">The description for the subnet.</span></span>  <br/> |
   

