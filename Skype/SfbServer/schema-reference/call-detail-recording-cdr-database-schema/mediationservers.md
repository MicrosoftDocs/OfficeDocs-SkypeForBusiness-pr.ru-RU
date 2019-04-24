---
title: Таблица MediationServers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: Таблица mediationservers представляет собой вспомогательную таблицу. Каждая запись сохранение информации о один сервер-посредник, задействованных в вызовах с записями в базе данных.
ms.openlocfilehash: 77173fbb81bc2046a1906c61456f607ec7f2b5b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212903"
---
# <a name="mediationservers-table"></a><span data-ttu-id="28108-104">Таблица MediationServers</span><span class="sxs-lookup"><span data-stu-id="28108-104">MediationServers table</span></span>
 
<span data-ttu-id="28108-105">Таблица mediationservers представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="28108-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="28108-106">Каждая запись сохранение информации о один сервер-посредник, задействованных в вызовах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="28108-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="28108-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="28108-107">**Column**</span></span>|<span data-ttu-id="28108-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="28108-108">**Data Type**</span></span>|<span data-ttu-id="28108-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="28108-109">**Key/Index**</span></span>|<span data-ttu-id="28108-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="28108-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28108-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="28108-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="28108-112">целое</span><span class="sxs-lookup"><span data-stu-id="28108-112">int</span></span>  <br/> |<span data-ttu-id="28108-113">Primary</span><span class="sxs-lookup"><span data-stu-id="28108-113">Primary</span></span>  <br/> |<span data-ttu-id="28108-114">Уникальный номер, идентифицирующий этот сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="28108-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="28108-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="28108-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="28108-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="28108-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="28108-117">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="28108-117">Mediation Server name.</span></span>  <br/> |
   

