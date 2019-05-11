---
title: Таблица edgeservers в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица edgeservers представляет собой вспомогательную таблицу. Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.
ms.openlocfilehash: a55a72f9a98dda0295256803a7f9318116ecf969
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901054"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="857c2-104">Таблица edgeservers в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="857c2-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="857c2-105">Таблица edgeservers представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="857c2-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="857c2-106">Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="857c2-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="857c2-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="857c2-107">**Column**</span></span>|<span data-ttu-id="857c2-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="857c2-108">**Data Type**</span></span>|<span data-ttu-id="857c2-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="857c2-109">**Key/Index**</span></span>|<span data-ttu-id="857c2-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="857c2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="857c2-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="857c2-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="857c2-112">целое</span><span class="sxs-lookup"><span data-stu-id="857c2-112">int</span></span>  <br/> |<span data-ttu-id="857c2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="857c2-113">Primary</span></span>  <br/> |<span data-ttu-id="857c2-114">Уникальный номер, идентифицирующий этот пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="857c2-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="857c2-115">**Пограничный сервер**</span><span class="sxs-lookup"><span data-stu-id="857c2-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="857c2-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="857c2-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="857c2-117">Имя пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="857c2-117">Edge Server name.</span></span>  <br/> |
   

