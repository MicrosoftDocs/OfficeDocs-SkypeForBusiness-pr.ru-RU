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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212525"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="6afb0-104">Таблица MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="6afb0-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="6afb0-105">Таблица monitoredusersitelink представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="6afb0-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="6afb0-106">Каждая запись представляет одну ссылку между двумя узлами пользователя.</span><span class="sxs-lookup"><span data-stu-id="6afb0-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="6afb0-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6afb0-107">**Column**</span></span>|<span data-ttu-id="6afb0-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6afb0-108">**Data Type**</span></span>|<span data-ttu-id="6afb0-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="6afb0-109">**Key/Index**</span></span>|<span data-ttu-id="6afb0-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6afb0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6afb0-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="6afb0-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="6afb0-112">целое</span><span class="sxs-lookup"><span data-stu-id="6afb0-112">int</span></span>  <br/> |<span data-ttu-id="6afb0-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="6afb0-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6afb0-114">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="6afb0-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="6afb0-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="6afb0-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="6afb0-116">целое</span><span class="sxs-lookup"><span data-stu-id="6afb0-116">int</span></span>  <br/> |<span data-ttu-id="6afb0-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="6afb0-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6afb0-118">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="6afb0-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

