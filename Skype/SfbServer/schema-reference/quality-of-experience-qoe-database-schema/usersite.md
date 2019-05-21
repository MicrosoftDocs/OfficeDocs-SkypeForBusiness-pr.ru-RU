---
title: Таблица UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблица Усерсите является вспомогательной таблицей. Каждая запись соответствует одному сайту пользователя, определенному в параметрах конфигурации сети.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294574"
---
# <a name="usersite-table"></a><span data-ttu-id="9af2f-104">Таблица UserSite</span><span class="sxs-lookup"><span data-stu-id="9af2f-104">UserSite table</span></span>
 
<span data-ttu-id="9af2f-105">Таблица Усерсите является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="9af2f-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="9af2f-106">Каждая запись соответствует одному сайту пользователя, определенному в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="9af2f-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="9af2f-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9af2f-107">**Column**</span></span>|<span data-ttu-id="9af2f-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9af2f-108">**Data Type**</span></span>|<span data-ttu-id="9af2f-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="9af2f-109">**Key/Index**</span></span>|<span data-ttu-id="9af2f-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9af2f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9af2f-111">**Усерситекэй**</span><span class="sxs-lookup"><span data-stu-id="9af2f-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="9af2f-112">целое</span><span class="sxs-lookup"><span data-stu-id="9af2f-112">int</span></span>  <br/> |<span data-ttu-id="9af2f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9af2f-113">Primary</span></span>  <br/> |<span data-ttu-id="9af2f-114">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="9af2f-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="9af2f-115">**Усерситенаме**</span><span class="sxs-lookup"><span data-stu-id="9af2f-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="9af2f-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9af2f-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="9af2f-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="9af2f-117">Unique</span></span>  <br/> |<span data-ttu-id="9af2f-118">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="9af2f-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="9af2f-119">**Регионкэй**</span><span class="sxs-lookup"><span data-stu-id="9af2f-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="9af2f-120">целое</span><span class="sxs-lookup"><span data-stu-id="9af2f-120">int</span></span>  <br/> |<span data-ttu-id="9af2f-121">Другом</span><span class="sxs-lookup"><span data-stu-id="9af2f-121">Foreign</span></span>  <br/> |<span data-ttu-id="9af2f-122">Ссылка на из [таблицы Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="9af2f-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

