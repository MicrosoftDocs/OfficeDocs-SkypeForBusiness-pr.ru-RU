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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212090"
---
# <a name="subnet-table"></a><span data-ttu-id="298ae-104">Таблица Subnet</span><span class="sxs-lookup"><span data-stu-id="298ae-104">Subnet table</span></span>
 
<span data-ttu-id="298ae-105">Таблица Subnet представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="298ae-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="298ae-106">Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="298ae-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="298ae-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="298ae-107">**Column**</span></span>|<span data-ttu-id="298ae-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="298ae-108">**Data Type**</span></span>|<span data-ttu-id="298ae-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="298ae-109">**Key/Index**</span></span>|<span data-ttu-id="298ae-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="298ae-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="298ae-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="298ae-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="298ae-112">целое</span><span class="sxs-lookup"><span data-stu-id="298ae-112">int</span></span>  <br/> |<span data-ttu-id="298ae-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="298ae-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="298ae-114">Целое число, представляющее IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="298ae-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="298ae-115">**Маска подсети**</span><span class="sxs-lookup"><span data-stu-id="298ae-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="298ae-116">целое</span><span class="sxs-lookup"><span data-stu-id="298ae-116">int</span></span>  <br/> ||<span data-ttu-id="298ae-117">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="298ae-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="298ae-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="298ae-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="298ae-119">целое</span><span class="sxs-lookup"><span data-stu-id="298ae-119">int</span></span>  <br/> |<span data-ttu-id="298ae-120">Внешний</span><span class="sxs-lookup"><span data-stu-id="298ae-120">Foreign</span></span>  <br/> |<span data-ttu-id="298ae-121">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="298ae-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="298ae-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="298ae-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="298ae-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="298ae-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="298ae-124">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="298ae-124">The description for the subnet.</span></span>  <br/> |
   

