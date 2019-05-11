---
title: Таблица UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблицы UserSite table представляет собой вспомогательную таблицу. Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906955"
---
# <a name="usersite-table"></a><span data-ttu-id="7b9e6-104">Таблица UserSite</span><span class="sxs-lookup"><span data-stu-id="7b9e6-104">UserSite table</span></span>
 
<span data-ttu-id="7b9e6-105">Таблицы UserSite table представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="7b9e6-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="7b9e6-106">Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="7b9e6-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="7b9e6-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7b9e6-107">**Column**</span></span>|<span data-ttu-id="7b9e6-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7b9e6-108">**Data Type**</span></span>|<span data-ttu-id="7b9e6-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7b9e6-109">**Key/Index**</span></span>|<span data-ttu-id="7b9e6-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7b9e6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b9e6-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="7b9e6-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="7b9e6-112">целое</span><span class="sxs-lookup"><span data-stu-id="7b9e6-112">int</span></span>  <br/> |<span data-ttu-id="7b9e6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7b9e6-113">Primary</span></span>  <br/> |<span data-ttu-id="7b9e6-114">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b9e6-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="7b9e6-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="7b9e6-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="7b9e6-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="7b9e6-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="7b9e6-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="7b9e6-117">Unique</span></span>  <br/> |<span data-ttu-id="7b9e6-118">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b9e6-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="7b9e6-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="7b9e6-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="7b9e6-120">целое</span><span class="sxs-lookup"><span data-stu-id="7b9e6-120">int</span></span>  <br/> |<span data-ttu-id="7b9e6-121">Внешний</span><span class="sxs-lookup"><span data-stu-id="7b9e6-121">Foreign</span></span>  <br/> |<span data-ttu-id="7b9e6-122">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="7b9e6-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

