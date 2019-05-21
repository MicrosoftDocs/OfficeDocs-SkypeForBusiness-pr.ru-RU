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
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Таблица Нетворкконнектиондетаил сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294819"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="2b669-104">Таблица Нетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="2b669-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="2b669-105">Таблица Нетворкконнектиондетаил сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2b669-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="2b669-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b669-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2b669-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2b669-107">**Column**</span></span>|<span data-ttu-id="2b669-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2b669-108">**Data Type**</span></span>|<span data-ttu-id="2b669-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="2b669-109">**Key/Index**</span></span>|<span data-ttu-id="2b669-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="2b669-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b669-111">**Нетворкконнектиондетаилкэй**</span><span class="sxs-lookup"><span data-stu-id="2b669-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="2b669-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="2b669-112">tinyint</span></span>  <br/> |<span data-ttu-id="2b669-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2b669-113">Primary</span></span>  <br/> |<span data-ttu-id="2b669-114">Уникальный идентификатор типа сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="2b669-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="2b669-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="2b669-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="2b669-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b669-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="2b669-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="2b669-117">Unique</span></span>  <br/> |<span data-ttu-id="2b669-118">Тип сетевого подключения, соответствующий Нетворкконнектиондетаилкэй.</span><span class="sxs-lookup"><span data-stu-id="2b669-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="2b669-119">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2b669-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="2b669-120">0--проводное подключение</span><span class="sxs-lookup"><span data-stu-id="2b669-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="2b669-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="2b669-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="2b669-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="2b669-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="2b669-123">3--Мобилебб</span><span class="sxs-lookup"><span data-stu-id="2b669-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="2b669-124">4 – другие</span><span class="sxs-lookup"><span data-stu-id="2b669-124">4 -- Other</span></span>  <br/> <span data-ttu-id="2b669-125">5--туннель</span><span class="sxs-lookup"><span data-stu-id="2b669-125">5 -- Tunnel</span></span>  <br/> |
   

