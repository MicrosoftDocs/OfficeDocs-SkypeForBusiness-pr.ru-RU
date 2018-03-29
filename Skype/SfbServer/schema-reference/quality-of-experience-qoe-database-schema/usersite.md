---
title: Таблица UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблицы UserSite table представляет собой вспомогательную таблицу. Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a><span data-ttu-id="c92b2-104">Таблица UserSite</span><span class="sxs-lookup"><span data-stu-id="c92b2-104">UserSite table</span></span>
 
<span data-ttu-id="c92b2-105">Таблицы UserSite table представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="c92b2-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="c92b2-106">Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="c92b2-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="c92b2-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c92b2-107">**Column**</span></span>|<span data-ttu-id="c92b2-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c92b2-108">**Data Type**</span></span>|<span data-ttu-id="c92b2-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="c92b2-109">**Key/Index**</span></span>|<span data-ttu-id="c92b2-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c92b2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c92b2-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="c92b2-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="c92b2-112">целое</span><span class="sxs-lookup"><span data-stu-id="c92b2-112">int</span></span>  <br/> |<span data-ttu-id="c92b2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c92b2-113">Primary</span></span>  <br/> |<span data-ttu-id="c92b2-114">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="c92b2-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="c92b2-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="c92b2-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="c92b2-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="c92b2-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="c92b2-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="c92b2-117">Unique</span></span>  <br/> |<span data-ttu-id="c92b2-118">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="c92b2-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="c92b2-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="c92b2-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="c92b2-120">целое</span><span class="sxs-lookup"><span data-stu-id="c92b2-120">int</span></span>  <br/> |<span data-ttu-id="c92b2-121">Внешний</span><span class="sxs-lookup"><span data-stu-id="c92b2-121">Foreign</span></span>  <br/> |<span data-ttu-id="c92b2-122">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="c92b2-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

