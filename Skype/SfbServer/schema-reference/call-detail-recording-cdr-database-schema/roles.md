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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Таблица ролей — это статическая таблица, в которой хранится список возможных ролей конференции, таких как участники и выступающие.
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295897"
---
# <a name="roles-table"></a><span data-ttu-id="cf782-103">Таблица Roles</span><span class="sxs-lookup"><span data-stu-id="cf782-103">Roles table</span></span>
 
<span data-ttu-id="cf782-104">Таблица ролей — это статическая таблица, в которой хранится список возможных ролей конференции, таких как участники и выступающие.</span><span class="sxs-lookup"><span data-stu-id="cf782-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="cf782-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="cf782-105">**Column**</span></span>|<span data-ttu-id="cf782-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="cf782-106">**Data Type**</span></span>|<span data-ttu-id="cf782-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="cf782-107">**Key/Index**</span></span>|<span data-ttu-id="cf782-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="cf782-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf782-109">**Ролеид**</span><span class="sxs-lookup"><span data-stu-id="cf782-109">**RoleId**</span></span> <br/> |<span data-ttu-id="cf782-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="cf782-110">tinyint</span></span>  <br/> |<span data-ttu-id="cf782-111">Primary</span><span class="sxs-lookup"><span data-stu-id="cf782-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="cf782-112">**Роль**</span><span class="sxs-lookup"><span data-stu-id="cf782-112">**Role**</span></span> <br/> |<span data-ttu-id="cf782-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cf782-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="cf782-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cf782-114">Allowed values:</span></span> <br/>  <span data-ttu-id="cf782-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="cf782-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="cf782-116">1 — выступающий</span><span class="sxs-lookup"><span data-stu-id="cf782-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="cf782-117">2 участника</span><span class="sxs-lookup"><span data-stu-id="cf782-117">2 - Attendee</span></span> <br/> |
   

