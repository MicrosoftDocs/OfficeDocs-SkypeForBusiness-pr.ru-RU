---
title: Таблица MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806359"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="f68ef-104">Таблица MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="f68ef-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="f68ef-p102">Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.</span><span class="sxs-lookup"><span data-stu-id="f68ef-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="f68ef-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f68ef-107">**Column**</span></span>|<span data-ttu-id="f68ef-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="f68ef-108">**Data Type**</span></span>|<span data-ttu-id="f68ef-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="f68ef-109">**Key/Index**</span></span>|<span data-ttu-id="f68ef-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f68ef-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f68ef-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="f68ef-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="f68ef-112">int</span><span class="sxs-lookup"><span data-stu-id="f68ef-112">int</span></span>  <br/> |<span data-ttu-id="f68ef-113">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="f68ef-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f68ef-114">Ссылка из [таблицы UserSite.](usersite.md)</span><span class="sxs-lookup"><span data-stu-id="f68ef-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="f68ef-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="f68ef-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="f68ef-116">int</span><span class="sxs-lookup"><span data-stu-id="f68ef-116">int</span></span>  <br/> |<span data-ttu-id="f68ef-117">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="f68ef-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f68ef-118">Ссылка из [таблицы UserSite.](usersite.md)</span><span class="sxs-lookup"><span data-stu-id="f68ef-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

