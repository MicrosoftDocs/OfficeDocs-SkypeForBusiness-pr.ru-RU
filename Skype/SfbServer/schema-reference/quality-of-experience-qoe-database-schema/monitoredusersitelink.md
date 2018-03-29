---
title: Таблица MonitoredUserSiteLink
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
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="9417c-104">Таблица MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="9417c-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="9417c-105">Таблица monitoredusersitelink представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="9417c-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="9417c-106">Каждая запись представляет одну ссылку между двумя узлами пользователя.</span><span class="sxs-lookup"><span data-stu-id="9417c-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="9417c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9417c-107">**Column**</span></span>|<span data-ttu-id="9417c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9417c-108">**Data Type**</span></span>|<span data-ttu-id="9417c-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="9417c-109">**Key/Index**</span></span>|<span data-ttu-id="9417c-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9417c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9417c-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="9417c-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="9417c-112">целое</span><span class="sxs-lookup"><span data-stu-id="9417c-112">int</span></span>  <br/> |<span data-ttu-id="9417c-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="9417c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9417c-114">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="9417c-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="9417c-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="9417c-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="9417c-116">целое</span><span class="sxs-lookup"><span data-stu-id="9417c-116">int</span></span>  <br/> |<span data-ttu-id="9417c-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="9417c-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9417c-118">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="9417c-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

