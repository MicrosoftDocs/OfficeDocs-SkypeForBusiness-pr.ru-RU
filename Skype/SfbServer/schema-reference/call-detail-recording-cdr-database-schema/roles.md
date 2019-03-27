---
title: Таблица Roles
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Таблица Roles — это статическая таблица, в которой хранится список возможных ролей участников конференции, такие как участник и докладчик.
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891715"
---
# <a name="roles-table"></a><span data-ttu-id="7572e-103">Таблица Roles</span><span class="sxs-lookup"><span data-stu-id="7572e-103">Roles table</span></span>
 
<span data-ttu-id="7572e-104">Таблица Roles — это статическая таблица, в которой хранится список возможных ролей участников конференции, такие как участник и докладчик.</span><span class="sxs-lookup"><span data-stu-id="7572e-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="7572e-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7572e-105">**Column**</span></span>|<span data-ttu-id="7572e-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7572e-106">**Data Type**</span></span>|<span data-ttu-id="7572e-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7572e-107">**Key/Index**</span></span>|<span data-ttu-id="7572e-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7572e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7572e-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="7572e-109">**RoleId**</span></span> <br/> |<span data-ttu-id="7572e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7572e-110">tinyint</span></span>  <br/> |<span data-ttu-id="7572e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7572e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="7572e-112">**Роль**</span><span class="sxs-lookup"><span data-stu-id="7572e-112">**Role**</span></span> <br/> |<span data-ttu-id="7572e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7572e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7572e-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7572e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="7572e-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="7572e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="7572e-116">1 — выступающего</span><span class="sxs-lookup"><span data-stu-id="7572e-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="7572e-117">2 — attendee</span><span class="sxs-lookup"><span data-stu-id="7572e-117">2 - Attendee</span></span> <br/> |
   

