---
title: Таблица edgeservers в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица edgeservers представляет собой вспомогательную таблицу. Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.
ms.openlocfilehash: 253190f23d130d12a1b4af701bf68922717d8da8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874013"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c35a2-104">Таблица edgeservers в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c35a2-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c35a2-105">Таблица edgeservers представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="c35a2-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="c35a2-106">Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c35a2-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="c35a2-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c35a2-107">**Column**</span></span>|<span data-ttu-id="c35a2-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c35a2-108">**Data Type**</span></span>|<span data-ttu-id="c35a2-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="c35a2-109">**Key/Index**</span></span>|<span data-ttu-id="c35a2-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c35a2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c35a2-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="c35a2-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="c35a2-112">целое</span><span class="sxs-lookup"><span data-stu-id="c35a2-112">int</span></span>  <br/> |<span data-ttu-id="c35a2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c35a2-113">Primary</span></span>  <br/> |<span data-ttu-id="c35a2-114">Уникальный номер, идентифицирующий этот пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="c35a2-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="c35a2-115">**Пограничный сервер**</span><span class="sxs-lookup"><span data-stu-id="c35a2-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="c35a2-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c35a2-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="c35a2-117">Имя пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="c35a2-117">Edge Server name.</span></span>  <br/> |
   

