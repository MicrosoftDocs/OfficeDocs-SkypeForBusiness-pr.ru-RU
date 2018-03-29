---
title: Таблица MediationServers
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
ms.openlocfilehash: 5854e9787497316d76b7262821be8d4953532d56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="mediationservers-table"></a><span data-ttu-id="2eaef-104">Таблица MediationServers</span><span class="sxs-lookup"><span data-stu-id="2eaef-104">MediationServers table</span></span>
 
<span data-ttu-id="2eaef-105">Таблица mediationservers представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="2eaef-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="2eaef-106">Каждая запись сохранение информации о один сервер-посредник, задействованных в вызовах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2eaef-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="2eaef-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2eaef-107">**Column**</span></span>|<span data-ttu-id="2eaef-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2eaef-108">**Data Type**</span></span>|<span data-ttu-id="2eaef-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="2eaef-109">**Key/Index**</span></span>|<span data-ttu-id="2eaef-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="2eaef-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2eaef-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="2eaef-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="2eaef-112">целое</span><span class="sxs-lookup"><span data-stu-id="2eaef-112">int</span></span>  <br/> |<span data-ttu-id="2eaef-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2eaef-113">Primary</span></span>  <br/> |<span data-ttu-id="2eaef-114">Уникальный номер, идентифицирующий этот сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="2eaef-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="2eaef-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="2eaef-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="2eaef-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2eaef-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="2eaef-117">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="2eaef-117">Mediation Server name.</span></span>  <br/> |
   

