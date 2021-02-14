---
title: Таблица Gateways в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Таблица Gateways является вспомогательной. В каждой записи хранится информация об одном шлюзе, который участвует в вызовах телефонной сети общего звонков (PSTN), в базе данных которых есть записи.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821589"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7bf40-104">Таблица Gateways в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7bf40-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7bf40-105">Таблица Gateways является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="7bf40-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="7bf40-106">В каждой записи хранится информация об одном шлюзе, который участвует в вызовах телефонной сети общего звонков (PSTN), в базе данных которых есть записи.</span><span class="sxs-lookup"><span data-stu-id="7bf40-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="7bf40-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7bf40-107">**Column**</span></span>|<span data-ttu-id="7bf40-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7bf40-108">**Data Type**</span></span>|<span data-ttu-id="7bf40-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7bf40-109">**Key/Index**</span></span>|<span data-ttu-id="7bf40-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7bf40-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7bf40-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="7bf40-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="7bf40-112">int</span><span class="sxs-lookup"><span data-stu-id="7bf40-112">int</span></span>  <br/> |<span data-ttu-id="7bf40-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7bf40-113">Primary</span></span>  <br/> |<span data-ttu-id="7bf40-114">Уникальный номер, идентифицирующий этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="7bf40-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="7bf40-115">**Шлюз**</span><span class="sxs-lookup"><span data-stu-id="7bf40-115">**Gateway**</span></span> <br/> |<span data-ttu-id="7bf40-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7bf40-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="7bf40-117">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="7bf40-117">Gateway name.</span></span>  <br/> |
   

