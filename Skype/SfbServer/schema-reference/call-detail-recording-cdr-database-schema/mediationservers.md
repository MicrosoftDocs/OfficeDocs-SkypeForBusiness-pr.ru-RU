---
title: Таблица MediationServers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: Таблица mediationservers представляет собой вспомогательную таблицу. Каждая запись сохранение информации о один сервер-посредник, задействованных в вызовах с записями в базе данных.
ms.openlocfilehash: 25f6c14a903ffde424cba1c2a6bb3292040b2391
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930548"
---
# <a name="mediationservers-table"></a><span data-ttu-id="2400d-104">Таблица MediationServers</span><span class="sxs-lookup"><span data-stu-id="2400d-104">MediationServers table</span></span>
 
<span data-ttu-id="2400d-105">Таблица mediationservers представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="2400d-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="2400d-106">Каждая запись сохранение информации о один сервер-посредник, задействованных в вызовах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2400d-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="2400d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2400d-107">**Column**</span></span>|<span data-ttu-id="2400d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2400d-108">**Data Type**</span></span>|<span data-ttu-id="2400d-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="2400d-109">**Key/Index**</span></span>|<span data-ttu-id="2400d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="2400d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2400d-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="2400d-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="2400d-112">целое</span><span class="sxs-lookup"><span data-stu-id="2400d-112">int</span></span>  <br/> |<span data-ttu-id="2400d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2400d-113">Primary</span></span>  <br/> |<span data-ttu-id="2400d-114">Уникальный номер, идентифицирующий этот сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="2400d-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="2400d-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="2400d-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="2400d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2400d-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="2400d-117">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="2400d-117">Mediation Server name.</span></span>  <br/> |
   

