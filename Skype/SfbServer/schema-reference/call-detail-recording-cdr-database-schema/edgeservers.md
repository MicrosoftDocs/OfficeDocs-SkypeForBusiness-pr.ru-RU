---
title: Таблица edgeservers в Скайп для Business Server 2015
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
ms.openlocfilehash: 581dfcb6bbd3b5088af2bbc27a580d791b9ef8f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2baae-104">Таблица edgeservers в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2baae-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2baae-105">Таблица edgeservers представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="2baae-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="2baae-106">Каждая запись сохраняет сведения об одном пограничном сервере, задействованных в вызовы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2baae-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="2baae-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2baae-107">**Column**</span></span>|<span data-ttu-id="2baae-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2baae-108">**Data Type**</span></span>|<span data-ttu-id="2baae-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="2baae-109">**Key/Index**</span></span>|<span data-ttu-id="2baae-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="2baae-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2baae-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="2baae-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="2baae-112">целое</span><span class="sxs-lookup"><span data-stu-id="2baae-112">int</span></span>  <br/> |<span data-ttu-id="2baae-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2baae-113">Primary</span></span>  <br/> |<span data-ttu-id="2baae-114">Уникальный номер, идентифицирующий этот пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="2baae-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="2baae-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="2baae-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="2baae-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2baae-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="2baae-117">Имя пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2baae-117">Edge Server name.</span></span>  <br/> |
   

