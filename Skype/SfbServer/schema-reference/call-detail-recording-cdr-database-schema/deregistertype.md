---
title: Таблица Дерегистертипе в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Таблица Дерегистертипе — это статическая таблица, в которой хранится список возможных типов отмены регистров пользователей, например "инициировано клиентом", "регистрация просрочено" или "клиент перестает отвечать на запросы".
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296352"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="498e4-103">Таблица Дерегистертипе в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="498e4-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="498e4-104">Таблица Дерегистертипе — это статическая таблица, в которой хранится список возможных типов отмены регистров пользователей, например "инициировано клиентом", "регистрация просрочено" или "клиент перестает отвечать на запросы".</span><span class="sxs-lookup"><span data-stu-id="498e4-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="498e4-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="498e4-105">**Column**</span></span>|<span data-ttu-id="498e4-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="498e4-106">**Data Type**</span></span>|<span data-ttu-id="498e4-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="498e4-107">**Key/Index**</span></span>|<span data-ttu-id="498e4-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="498e4-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="498e4-109">**Дерегистертипеид**</span><span class="sxs-lookup"><span data-stu-id="498e4-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="498e4-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="498e4-110">tinyint</span></span>  <br/> |<span data-ttu-id="498e4-111">Primary</span><span class="sxs-lookup"><span data-stu-id="498e4-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="498e4-112">**Дерегистерреасон**</span><span class="sxs-lookup"><span data-stu-id="498e4-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="498e4-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="498e4-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="498e4-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="498e4-114">Allowed values:</span></span> <br/>  <span data-ttu-id="498e4-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="498e4-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="498e4-116">1 — клиент инициировал отмену регистрации</span><span class="sxs-lookup"><span data-stu-id="498e4-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="498e4-117">2 — срок действия регистрации истек</span><span class="sxs-lookup"><span data-stu-id="498e4-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="498e4-118">3-Клиент аварийно завершил работу</span><span class="sxs-lookup"><span data-stu-id="498e4-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="498e4-119">4 — изменились атрибуты пользователя</span><span class="sxs-lookup"><span data-stu-id="498e4-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="498e4-120">5 — основной регистратор изменился</span><span class="sxs-lookup"><span data-stu-id="498e4-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="498e4-121">6 — устаревший клиент в режиме выживания</span><span class="sxs-lookup"><span data-stu-id="498e4-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

