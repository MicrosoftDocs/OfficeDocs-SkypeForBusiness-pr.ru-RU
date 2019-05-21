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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица подсети является вспомогательной таблицей. Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294637"
---
# <a name="subnet-table"></a><span data-ttu-id="99553-104">Таблица Subnet</span><span class="sxs-lookup"><span data-stu-id="99553-104">Subnet table</span></span>
 
<span data-ttu-id="99553-105">Таблица подсети является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="99553-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="99553-106">Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="99553-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="99553-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="99553-107">**Column**</span></span>|<span data-ttu-id="99553-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="99553-108">**Data Type**</span></span>|<span data-ttu-id="99553-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="99553-109">**Key/Index**</span></span>|<span data-ttu-id="99553-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="99553-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="99553-111">**Субнетип**</span><span class="sxs-lookup"><span data-stu-id="99553-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="99553-112">целое</span><span class="sxs-lookup"><span data-stu-id="99553-112">int</span></span>  <br/> |<span data-ttu-id="99553-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="99553-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="99553-114">Целочисленное представление для IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="99553-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="99553-115">**Сети**</span><span class="sxs-lookup"><span data-stu-id="99553-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="99553-116">целое</span><span class="sxs-lookup"><span data-stu-id="99553-116">int</span></span>  <br/> ||<span data-ttu-id="99553-117">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="99553-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="99553-118">**Усерситекэй**</span><span class="sxs-lookup"><span data-stu-id="99553-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="99553-119">целое</span><span class="sxs-lookup"><span data-stu-id="99553-119">int</span></span>  <br/> |<span data-ttu-id="99553-120">Другом</span><span class="sxs-lookup"><span data-stu-id="99553-120">Foreign</span></span>  <br/> |<span data-ttu-id="99553-121">На которую ссылается [Таблица усерсите](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="99553-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="99553-122">**Субнетдескриптион**</span><span class="sxs-lookup"><span data-stu-id="99553-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="99553-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="99553-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="99553-124">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="99553-124">The description for the subnet.</span></span>  <br/> |
   

