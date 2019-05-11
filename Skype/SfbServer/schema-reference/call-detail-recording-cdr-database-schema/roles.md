---
title: Таблица Roles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Таблица Roles — это статическая таблица, в которой хранится список возможных ролей участников конференции, такие как участник и докладчик.
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930306"
---
# <a name="roles-table"></a><span data-ttu-id="258ed-103">Таблица Roles</span><span class="sxs-lookup"><span data-stu-id="258ed-103">Roles table</span></span>
 
<span data-ttu-id="258ed-104">Таблица Roles — это статическая таблица, в которой хранится список возможных ролей участников конференции, такие как участник и докладчик.</span><span class="sxs-lookup"><span data-stu-id="258ed-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="258ed-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="258ed-105">**Column**</span></span>|<span data-ttu-id="258ed-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="258ed-106">**Data Type**</span></span>|<span data-ttu-id="258ed-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="258ed-107">**Key/Index**</span></span>|<span data-ttu-id="258ed-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="258ed-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="258ed-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="258ed-109">**RoleId**</span></span> <br/> |<span data-ttu-id="258ed-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="258ed-110">tinyint</span></span>  <br/> |<span data-ttu-id="258ed-111">Primary</span><span class="sxs-lookup"><span data-stu-id="258ed-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="258ed-112">**Роль**</span><span class="sxs-lookup"><span data-stu-id="258ed-112">**Role**</span></span> <br/> |<span data-ttu-id="258ed-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="258ed-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="258ed-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="258ed-114">Allowed values:</span></span> <br/>  <span data-ttu-id="258ed-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="258ed-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="258ed-116">1 — выступающего</span><span class="sxs-lookup"><span data-stu-id="258ed-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="258ed-117">2 — attendee</span><span class="sxs-lookup"><span data-stu-id="258ed-117">2 - Attendee</span></span> <br/> |
   

