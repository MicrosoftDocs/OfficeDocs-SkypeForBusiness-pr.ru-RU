---
title: Таблица UserSite
ms.reviewer: ''
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
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212048"
---
# <a name="usersite-table"></a><span data-ttu-id="e3b87-104">Таблица UserSite</span><span class="sxs-lookup"><span data-stu-id="e3b87-104">UserSite table</span></span>
 
<span data-ttu-id="e3b87-105">Таблицы UserSite table представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="e3b87-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="e3b87-106">Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="e3b87-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="e3b87-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e3b87-107">**Column**</span></span>|<span data-ttu-id="e3b87-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e3b87-108">**Data Type**</span></span>|<span data-ttu-id="e3b87-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="e3b87-109">**Key/Index**</span></span>|<span data-ttu-id="e3b87-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e3b87-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e3b87-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="e3b87-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="e3b87-112">целое</span><span class="sxs-lookup"><span data-stu-id="e3b87-112">int</span></span>  <br/> |<span data-ttu-id="e3b87-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e3b87-113">Primary</span></span>  <br/> |<span data-ttu-id="e3b87-114">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3b87-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="e3b87-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="e3b87-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="e3b87-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="e3b87-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="e3b87-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="e3b87-117">Unique</span></span>  <br/> |<span data-ttu-id="e3b87-118">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3b87-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="e3b87-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="e3b87-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="e3b87-120">целое</span><span class="sxs-lookup"><span data-stu-id="e3b87-120">int</span></span>  <br/> |<span data-ttu-id="e3b87-121">Внешний</span><span class="sxs-lookup"><span data-stu-id="e3b87-121">Foreign</span></span>  <br/> |<span data-ttu-id="e3b87-122">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="e3b87-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

