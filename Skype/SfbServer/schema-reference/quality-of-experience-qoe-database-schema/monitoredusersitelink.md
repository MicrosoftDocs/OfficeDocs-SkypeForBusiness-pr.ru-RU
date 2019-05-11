---
title: Таблица MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица monitoredusersitelink представляет собой вспомогательную таблицу. Каждая запись представляет одну ссылку между двумя узлами пользователя.
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920014"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="44da9-104">Таблица MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="44da9-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="44da9-105">Таблица monitoredusersitelink представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="44da9-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="44da9-106">Каждая запись представляет одну ссылку между двумя узлами пользователя.</span><span class="sxs-lookup"><span data-stu-id="44da9-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="44da9-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="44da9-107">**Column**</span></span>|<span data-ttu-id="44da9-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="44da9-108">**Data Type**</span></span>|<span data-ttu-id="44da9-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="44da9-109">**Key/Index**</span></span>|<span data-ttu-id="44da9-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="44da9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44da9-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="44da9-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="44da9-112">целое</span><span class="sxs-lookup"><span data-stu-id="44da9-112">int</span></span>  <br/> |<span data-ttu-id="44da9-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="44da9-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="44da9-114">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="44da9-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="44da9-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="44da9-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="44da9-116">целое</span><span class="sxs-lookup"><span data-stu-id="44da9-116">int</span></span>  <br/> |<span data-ttu-id="44da9-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="44da9-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="44da9-118">Ссылка из [таблицы UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="44da9-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

