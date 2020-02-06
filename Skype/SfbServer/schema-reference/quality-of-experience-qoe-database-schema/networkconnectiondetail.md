---
title: Таблица Нетворкконнектиондетаил
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Таблица Нетворкконнектиондетаил сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807507"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="133e9-104">Таблица Нетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="133e9-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="133e9-105">Таблица Нетворкконнектиондетаил сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="133e9-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="133e9-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="133e9-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="133e9-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="133e9-107">**Column**</span></span>|<span data-ttu-id="133e9-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="133e9-108">**Data Type**</span></span>|<span data-ttu-id="133e9-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="133e9-109">**Key/Index**</span></span>|<span data-ttu-id="133e9-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="133e9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="133e9-111">**нетворкконнектиондетаилкэй**</span><span class="sxs-lookup"><span data-stu-id="133e9-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="133e9-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="133e9-112">tinyint</span></span>  <br/> |<span data-ttu-id="133e9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="133e9-113">Primary</span></span>  <br/> |<span data-ttu-id="133e9-114">Уникальный идентификатор типа сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="133e9-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="133e9-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="133e9-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="133e9-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="133e9-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="133e9-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="133e9-117">Unique</span></span>  <br/> |<span data-ttu-id="133e9-118">Тип сетевого подключения, соответствующий Нетворкконнектиондетаилкэй.</span><span class="sxs-lookup"><span data-stu-id="133e9-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="133e9-119">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="133e9-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="133e9-120">0--проводное подключение</span><span class="sxs-lookup"><span data-stu-id="133e9-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="133e9-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="133e9-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="133e9-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="133e9-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="133e9-123">3--Мобилебб</span><span class="sxs-lookup"><span data-stu-id="133e9-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="133e9-124">4 – другие</span><span class="sxs-lookup"><span data-stu-id="133e9-124">4 -- Other</span></span>  <br/> <span data-ttu-id="133e9-125">5--туннель</span><span class="sxs-lookup"><span data-stu-id="133e9-125">5 -- Tunnel</span></span>  <br/> |
   

