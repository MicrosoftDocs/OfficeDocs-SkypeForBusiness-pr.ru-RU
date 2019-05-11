---
title: Таблица шлюзы в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: В таблице шлюзов представляет собой вспомогательную таблицу. Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.
ms.openlocfilehash: 2a3429b45a63c0c7765f4e9da0ea2baf3f0d11b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901040"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8f40e-104">Таблица шлюзы в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8f40e-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8f40e-105">В таблице шлюзов представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="8f40e-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="8f40e-106">Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8f40e-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="8f40e-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8f40e-107">**Column**</span></span>|<span data-ttu-id="8f40e-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8f40e-108">**Data Type**</span></span>|<span data-ttu-id="8f40e-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8f40e-109">**Key/Index**</span></span>|<span data-ttu-id="8f40e-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8f40e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8f40e-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="8f40e-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="8f40e-112">целое</span><span class="sxs-lookup"><span data-stu-id="8f40e-112">int</span></span>  <br/> |<span data-ttu-id="8f40e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8f40e-113">Primary</span></span>  <br/> |<span data-ttu-id="8f40e-114">Уникальный номер, идентифицирующий этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="8f40e-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="8f40e-115">**Шлюз**</span><span class="sxs-lookup"><span data-stu-id="8f40e-115">**Gateway**</span></span> <br/> |<span data-ttu-id="8f40e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8f40e-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="8f40e-117">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="8f40e-117">Gateway name.</span></span>  <br/> |
   

