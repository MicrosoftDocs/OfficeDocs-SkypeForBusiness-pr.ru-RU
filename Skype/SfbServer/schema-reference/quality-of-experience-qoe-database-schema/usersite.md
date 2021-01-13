---
title: Таблица UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблица UserSite является вспомогательной. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799919"
---
# <a name="usersite-table"></a><span data-ttu-id="7d41e-104">Таблица UserSite</span><span class="sxs-lookup"><span data-stu-id="7d41e-104">UserSite table</span></span>
 
<span data-ttu-id="7d41e-105">Таблица UserSite является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="7d41e-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="7d41e-106">Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="7d41e-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="7d41e-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7d41e-107">**Column**</span></span>|<span data-ttu-id="7d41e-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7d41e-108">**Data Type**</span></span>|<span data-ttu-id="7d41e-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7d41e-109">**Key/Index**</span></span>|<span data-ttu-id="7d41e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7d41e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d41e-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="7d41e-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="7d41e-112">int</span><span class="sxs-lookup"><span data-stu-id="7d41e-112">int</span></span>  <br/> |<span data-ttu-id="7d41e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7d41e-113">Primary</span></span>  <br/> |<span data-ttu-id="7d41e-114">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d41e-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="7d41e-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="7d41e-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="7d41e-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="7d41e-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="7d41e-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="7d41e-117">Unique</span></span>  <br/> |<span data-ttu-id="7d41e-118">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d41e-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="7d41e-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="7d41e-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="7d41e-120">int</span><span class="sxs-lookup"><span data-stu-id="7d41e-120">int</span></span>  <br/> |<span data-ttu-id="7d41e-121">Внешняя</span><span class="sxs-lookup"><span data-stu-id="7d41e-121">Foreign</span></span>  <br/> |<span data-ttu-id="7d41e-122">Ссылка из [таблицы Region.](region.md)</span><span class="sxs-lookup"><span data-stu-id="7d41e-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

