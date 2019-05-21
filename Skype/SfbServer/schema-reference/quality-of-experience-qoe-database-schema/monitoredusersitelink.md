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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица Мониторедусерсителинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя сайтами пользователей.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294854"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="ce252-104">Таблица MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="ce252-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="ce252-105">Таблица Мониторедусерсителинк является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="ce252-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="ce252-106">Каждая запись представляет одну связь между двумя сайтами пользователей.</span><span class="sxs-lookup"><span data-stu-id="ce252-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="ce252-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ce252-107">**Column**</span></span>|<span data-ttu-id="ce252-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ce252-108">**Data Type**</span></span>|<span data-ttu-id="ce252-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ce252-109">**Key/Index**</span></span>|<span data-ttu-id="ce252-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ce252-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce252-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="ce252-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="ce252-112">целое</span><span class="sxs-lookup"><span data-stu-id="ce252-112">int</span></span>  <br/> |<span data-ttu-id="ce252-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="ce252-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ce252-114">На которую ссылается [Таблица усерсите](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="ce252-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ce252-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="ce252-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="ce252-116">целое</span><span class="sxs-lookup"><span data-stu-id="ce252-116">int</span></span>  <br/> |<span data-ttu-id="ce252-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="ce252-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ce252-118">Ссылка из [таблицы усерсите](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="ce252-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

