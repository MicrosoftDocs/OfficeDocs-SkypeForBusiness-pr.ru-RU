---
title: Таблица MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица monitoredusersitelink представляет собой вспомогательную таблицу. Каждая запись представляет одну ссылку между двумя узлами пользователя.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874261"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="d31dd-104">Таблица MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="d31dd-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="d31dd-105">Таблица monitoredusersitelink представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="d31dd-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="d31dd-106">Каждая запись представляет одну ссылку между двумя узлами пользователя.</span><span class="sxs-lookup"><span data-stu-id="d31dd-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="d31dd-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d31dd-107">**Column**</span></span>|<span data-ttu-id="d31dd-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d31dd-108">**Data Type**</span></span>|<span data-ttu-id="d31dd-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d31dd-109">**Key/Index**</span></span>|<span data-ttu-id="d31dd-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d31dd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d31dd-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="d31dd-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="d31dd-112">целое</span><span class="sxs-lookup"><span data-stu-id="d31dd-112">int</span></span>  <br/> |<span data-ttu-id="d31dd-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="d31dd-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d31dd-114">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="d31dd-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="d31dd-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="d31dd-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="d31dd-116">целое</span><span class="sxs-lookup"><span data-stu-id="d31dd-116">int</span></span>  <br/> |<span data-ttu-id="d31dd-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="d31dd-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d31dd-118">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="d31dd-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

