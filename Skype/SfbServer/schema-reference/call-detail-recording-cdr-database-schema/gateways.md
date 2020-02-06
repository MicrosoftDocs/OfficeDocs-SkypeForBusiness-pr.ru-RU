---
title: Таблица шлюзов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Таблица Gateways является вспомогательной таблицей. Каждая запись содержит сведения об одном шлюзе, который участвует в звонках по коммутируемой телефонной сети (PSTN), которые содержат записи в базе данных.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815167"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8086f-104">Таблица шлюзов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8086f-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8086f-105">Таблица Gateways является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="8086f-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="8086f-106">Каждая запись содержит сведения об одном шлюзе, который участвует в звонках по коммутируемой телефонной сети (PSTN), которые содержат записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8086f-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="8086f-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8086f-107">**Column**</span></span>|<span data-ttu-id="8086f-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8086f-108">**Data Type**</span></span>|<span data-ttu-id="8086f-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8086f-109">**Key/Index**</span></span>|<span data-ttu-id="8086f-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8086f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8086f-111">**гатевайид**</span><span class="sxs-lookup"><span data-stu-id="8086f-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="8086f-112">целое</span><span class="sxs-lookup"><span data-stu-id="8086f-112">int</span></span>  <br/> |<span data-ttu-id="8086f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8086f-113">Primary</span></span>  <br/> |<span data-ttu-id="8086f-114">Уникальный номер, идентифицирующий этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="8086f-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="8086f-115">**Шлюз**</span><span class="sxs-lookup"><span data-stu-id="8086f-115">**Gateway**</span></span> <br/> |<span data-ttu-id="8086f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8086f-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="8086f-117">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="8086f-117">Gateway name.</span></span>  <br/> |
   

