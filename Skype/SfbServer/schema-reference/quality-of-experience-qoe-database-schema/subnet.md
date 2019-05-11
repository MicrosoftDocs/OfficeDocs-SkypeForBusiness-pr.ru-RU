---
title: Таблица Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица Subnet представляет собой вспомогательную таблицу. Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907068"
---
# <a name="subnet-table"></a><span data-ttu-id="9243d-104">Таблица Subnet</span><span class="sxs-lookup"><span data-stu-id="9243d-104">Subnet table</span></span>
 
<span data-ttu-id="9243d-105">Таблица Subnet представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="9243d-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="9243d-106">Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="9243d-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="9243d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9243d-107">**Column**</span></span>|<span data-ttu-id="9243d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9243d-108">**Data Type**</span></span>|<span data-ttu-id="9243d-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="9243d-109">**Key/Index**</span></span>|<span data-ttu-id="9243d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9243d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9243d-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="9243d-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="9243d-112">целое</span><span class="sxs-lookup"><span data-stu-id="9243d-112">int</span></span>  <br/> |<span data-ttu-id="9243d-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="9243d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9243d-114">Целое число, представляющее IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="9243d-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="9243d-115">**Маска подсети**</span><span class="sxs-lookup"><span data-stu-id="9243d-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="9243d-116">целое</span><span class="sxs-lookup"><span data-stu-id="9243d-116">int</span></span>  <br/> ||<span data-ttu-id="9243d-117">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="9243d-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="9243d-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="9243d-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="9243d-119">целое</span><span class="sxs-lookup"><span data-stu-id="9243d-119">int</span></span>  <br/> |<span data-ttu-id="9243d-120">Внешний</span><span class="sxs-lookup"><span data-stu-id="9243d-120">Foreign</span></span>  <br/> |<span data-ttu-id="9243d-121">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="9243d-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="9243d-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="9243d-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="9243d-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="9243d-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="9243d-124">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="9243d-124">The description for the subnet.</span></span>  <br/> |
   

