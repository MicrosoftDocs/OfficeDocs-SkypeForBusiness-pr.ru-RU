---
title: Таблица Roles
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
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a><span data-ttu-id="fa4ac-103">Таблица Roles</span><span class="sxs-lookup"><span data-stu-id="fa4ac-103">Roles table</span></span>
 
<span data-ttu-id="fa4ac-104">Таблица Roles — это статическая таблица, в которой хранится список возможных ролей участников конференции, такие как участник и докладчик.</span><span class="sxs-lookup"><span data-stu-id="fa4ac-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="fa4ac-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fa4ac-105">**Column**</span></span>|<span data-ttu-id="fa4ac-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fa4ac-106">**Data Type**</span></span>|<span data-ttu-id="fa4ac-107">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="fa4ac-107">**Key/Index**</span></span>|<span data-ttu-id="fa4ac-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="fa4ac-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fa4ac-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="fa4ac-109">**RoleId**</span></span> <br/> |<span data-ttu-id="fa4ac-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="fa4ac-110">tinyint</span></span>  <br/> |<span data-ttu-id="fa4ac-111">Primary</span><span class="sxs-lookup"><span data-stu-id="fa4ac-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="fa4ac-112">**Role (Роль)**</span><span class="sxs-lookup"><span data-stu-id="fa4ac-112">**Role**</span></span> <br/> |<span data-ttu-id="fa4ac-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa4ac-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="fa4ac-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="fa4ac-114">Allowed values:</span></span> <br/>  <span data-ttu-id="fa4ac-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="fa4ac-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="fa4ac-116">1 — выступающего</span><span class="sxs-lookup"><span data-stu-id="fa4ac-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="fa4ac-117">2 — attendee</span><span class="sxs-lookup"><span data-stu-id="fa4ac-117">2 - Attendee</span></span> <br/> |
   

