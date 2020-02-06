---
title: Таблица Roles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Таблица ролей — это статическая таблица, в которой хранится список возможных ролей конференции, таких как участники и выступающие.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814937"
---
# <a name="roles-table"></a><span data-ttu-id="a7e03-103">Таблица Roles</span><span class="sxs-lookup"><span data-stu-id="a7e03-103">Roles table</span></span>
 
<span data-ttu-id="a7e03-104">Таблица ролей — это статическая таблица, в которой хранится список возможных ролей конференции, таких как участники и выступающие.</span><span class="sxs-lookup"><span data-stu-id="a7e03-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="a7e03-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a7e03-105">**Column**</span></span>|<span data-ttu-id="a7e03-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a7e03-106">**Data Type**</span></span>|<span data-ttu-id="a7e03-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a7e03-107">**Key/Index**</span></span>|<span data-ttu-id="a7e03-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a7e03-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7e03-109">**ролеид**</span><span class="sxs-lookup"><span data-stu-id="a7e03-109">**RoleId**</span></span> <br/> |<span data-ttu-id="a7e03-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7e03-110">tinyint</span></span>  <br/> |<span data-ttu-id="a7e03-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a7e03-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="a7e03-112">**Роль**</span><span class="sxs-lookup"><span data-stu-id="a7e03-112">**Role**</span></span> <br/> |<span data-ttu-id="a7e03-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7e03-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a7e03-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a7e03-114">Allowed values:</span></span> <br/>  <span data-ttu-id="a7e03-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="a7e03-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="a7e03-116">1 — выступающий</span><span class="sxs-lookup"><span data-stu-id="a7e03-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="a7e03-117">2 участника</span><span class="sxs-lookup"><span data-stu-id="a7e03-117">2 - Attendee</span></span> <br/> |
   

