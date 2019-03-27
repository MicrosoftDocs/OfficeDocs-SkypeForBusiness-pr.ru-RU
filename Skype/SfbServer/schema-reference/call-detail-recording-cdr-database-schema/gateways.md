---
title: Таблица шлюзы в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: В таблице шлюзов представляет собой вспомогательную таблицу. Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.
ms.openlocfilehash: 16860e924fb69f1dfe337e05c13d54fb66a8ed81
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899083"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e74b3-104">Таблица шлюзы в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e74b3-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e74b3-105">В таблице шлюзов представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="e74b3-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="e74b3-106">Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e74b3-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="e74b3-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e74b3-107">**Column**</span></span>|<span data-ttu-id="e74b3-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e74b3-108">**Data Type**</span></span>|<span data-ttu-id="e74b3-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="e74b3-109">**Key/Index**</span></span>|<span data-ttu-id="e74b3-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e74b3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e74b3-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="e74b3-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="e74b3-112">целое</span><span class="sxs-lookup"><span data-stu-id="e74b3-112">int</span></span>  <br/> |<span data-ttu-id="e74b3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e74b3-113">Primary</span></span>  <br/> |<span data-ttu-id="e74b3-114">Уникальный номер, идентифицирующий этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="e74b3-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="e74b3-115">**Шлюз**</span><span class="sxs-lookup"><span data-stu-id="e74b3-115">**Gateway**</span></span> <br/> |<span data-ttu-id="e74b3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74b3-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="e74b3-117">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="e74b3-117">Gateway name.</span></span>  <br/> |
   

