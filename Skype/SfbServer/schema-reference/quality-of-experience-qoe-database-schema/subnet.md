---
title: Таблица Subnet
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
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a><span data-ttu-id="1af84-104">Таблица Subnet</span><span class="sxs-lookup"><span data-stu-id="1af84-104">Subnet table</span></span>
 
<span data-ttu-id="1af84-105">Таблица Subnet представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="1af84-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="1af84-106">Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="1af84-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="1af84-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1af84-107">**Column**</span></span>|<span data-ttu-id="1af84-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1af84-108">**Data Type**</span></span>|<span data-ttu-id="1af84-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="1af84-109">**Key/Index**</span></span>|<span data-ttu-id="1af84-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="1af84-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1af84-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="1af84-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="1af84-112">целое</span><span class="sxs-lookup"><span data-stu-id="1af84-112">int</span></span>  <br/> |<span data-ttu-id="1af84-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="1af84-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1af84-114">Целое число, представляющее IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="1af84-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="1af84-115">**Маска подсети**</span><span class="sxs-lookup"><span data-stu-id="1af84-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="1af84-116">целое</span><span class="sxs-lookup"><span data-stu-id="1af84-116">int</span></span>  <br/> ||<span data-ttu-id="1af84-117">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="1af84-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="1af84-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="1af84-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="1af84-119">целое</span><span class="sxs-lookup"><span data-stu-id="1af84-119">int</span></span>  <br/> |<span data-ttu-id="1af84-120">Внешний</span><span class="sxs-lookup"><span data-stu-id="1af84-120">Foreign</span></span>  <br/> |<span data-ttu-id="1af84-121">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="1af84-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="1af84-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="1af84-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="1af84-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="1af84-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="1af84-124">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="1af84-124">The description for the subnet.</span></span>  <br/> |
   

