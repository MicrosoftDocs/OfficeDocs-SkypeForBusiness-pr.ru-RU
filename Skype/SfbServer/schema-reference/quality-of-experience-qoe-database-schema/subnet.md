---
title: Таблица Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица подсети является вспомогательной таблицей. Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805207"
---
# <a name="subnet-table"></a><span data-ttu-id="9aa9a-104">Таблица Subnet</span><span class="sxs-lookup"><span data-stu-id="9aa9a-104">Subnet table</span></span>
 
<span data-ttu-id="9aa9a-105">Таблица подсети является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="9aa9a-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="9aa9a-106">Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="9aa9a-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="9aa9a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-107">**Column**</span></span>|<span data-ttu-id="9aa9a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-108">**Data Type**</span></span>|<span data-ttu-id="9aa9a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-109">**Key/Index**</span></span>|<span data-ttu-id="9aa9a-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9aa9a-111">**субнетип**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="9aa9a-112">целое</span><span class="sxs-lookup"><span data-stu-id="9aa9a-112">int</span></span>  <br/> |<span data-ttu-id="9aa9a-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="9aa9a-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9aa9a-114">Целочисленное представление для IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="9aa9a-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="9aa9a-115">**Сети**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="9aa9a-116">целое</span><span class="sxs-lookup"><span data-stu-id="9aa9a-116">int</span></span>  <br/> ||<span data-ttu-id="9aa9a-117">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="9aa9a-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="9aa9a-118">**усерситекэй**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="9aa9a-119">целое</span><span class="sxs-lookup"><span data-stu-id="9aa9a-119">int</span></span>  <br/> |<span data-ttu-id="9aa9a-120">Другом</span><span class="sxs-lookup"><span data-stu-id="9aa9a-120">Foreign</span></span>  <br/> |<span data-ttu-id="9aa9a-121">На которую ссылается [Таблица усерсите](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9a-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="9aa9a-122">**субнетдескриптион**</span><span class="sxs-lookup"><span data-stu-id="9aa9a-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="9aa9a-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="9aa9a-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="9aa9a-124">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="9aa9a-124">The description for the subnet.</span></span>  <br/> |
   

