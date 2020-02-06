---
title: Таблица MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица Мониторедусерсителинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя сайтами пользователей.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807797"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="62492-104">Таблица MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="62492-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="62492-105">Таблица Мониторедусерсителинк является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="62492-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="62492-106">Каждая запись представляет одну связь между двумя сайтами пользователей.</span><span class="sxs-lookup"><span data-stu-id="62492-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="62492-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="62492-107">**Column**</span></span>|<span data-ttu-id="62492-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="62492-108">**Data Type**</span></span>|<span data-ttu-id="62492-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="62492-109">**Key/Index**</span></span>|<span data-ttu-id="62492-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="62492-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62492-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="62492-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="62492-112">целое</span><span class="sxs-lookup"><span data-stu-id="62492-112">int</span></span>  <br/> |<span data-ttu-id="62492-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="62492-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="62492-114">На которую ссылается [Таблица усерсите](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="62492-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="62492-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="62492-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="62492-116">целое</span><span class="sxs-lookup"><span data-stu-id="62492-116">int</span></span>  <br/> |<span data-ttu-id="62492-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="62492-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="62492-118">Ссылка из [таблицы усерсите](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="62492-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

