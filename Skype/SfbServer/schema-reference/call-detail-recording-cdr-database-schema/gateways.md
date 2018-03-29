---
title: Таблица шлюзы в Скайп для Business Server 2015
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
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3c1f1-104">Таблица шлюзы в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c1f1-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3c1f1-105">В таблице шлюзов представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="3c1f1-106">Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="3c1f1-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3c1f1-107">**Column**</span></span>|<span data-ttu-id="3c1f1-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3c1f1-108">**Data Type**</span></span>|<span data-ttu-id="3c1f1-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="3c1f1-109">**Key/Index**</span></span>|<span data-ttu-id="3c1f1-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="3c1f1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3c1f1-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="3c1f1-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="3c1f1-112">целое</span><span class="sxs-lookup"><span data-stu-id="3c1f1-112">int</span></span>  <br/> |<span data-ttu-id="3c1f1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3c1f1-113">Primary</span></span>  <br/> |<span data-ttu-id="3c1f1-114">Уникальный номер, идентифицирующий этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="3c1f1-115">**Шлюз**</span><span class="sxs-lookup"><span data-stu-id="3c1f1-115">**Gateway**</span></span> <br/> |<span data-ttu-id="3c1f1-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3c1f1-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="3c1f1-117">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-117">Gateway name.</span></span>  <br/> |
   

