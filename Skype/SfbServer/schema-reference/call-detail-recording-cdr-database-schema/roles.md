---
title: Таблица Roles
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809979"
---
# <a name="roles-table"></a><span data-ttu-id="04604-103">Таблица Roles</span><span class="sxs-lookup"><span data-stu-id="04604-103">Roles table</span></span>
 
<span data-ttu-id="04604-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span><span class="sxs-lookup"><span data-stu-id="04604-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="04604-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="04604-105">**Column**</span></span>|<span data-ttu-id="04604-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="04604-106">**Data Type**</span></span>|<span data-ttu-id="04604-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="04604-107">**Key/Index**</span></span>|<span data-ttu-id="04604-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="04604-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04604-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="04604-109">**RoleId**</span></span> <br/> |<span data-ttu-id="04604-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="04604-110">tinyint</span></span>  <br/> |<span data-ttu-id="04604-111">Primary</span><span class="sxs-lookup"><span data-stu-id="04604-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="04604-112">**Role**</span><span class="sxs-lookup"><span data-stu-id="04604-112">**Role**</span></span> <br/> |<span data-ttu-id="04604-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="04604-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="04604-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="04604-114">Allowed values:</span></span> <br/>  <span data-ttu-id="04604-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="04604-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="04604-116">1 — выступающий</span><span class="sxs-lookup"><span data-stu-id="04604-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="04604-117">2 — участник</span><span class="sxs-lookup"><span data-stu-id="04604-117">2 - Attendee</span></span> <br/> |
   

