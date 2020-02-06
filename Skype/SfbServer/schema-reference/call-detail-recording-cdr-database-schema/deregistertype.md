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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Таблица Дерегистертипе — это статическая таблица, в которой хранится список возможных типов отмены регистров пользователей, например "инициировано клиентом", "регистрация просрочено" или "клиент перестает отвечать на запросы".
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815297"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9d4fe-103">Таблица Дерегистертипе в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d4fe-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9d4fe-104">Таблица Дерегистертипе — это статическая таблица, в которой хранится список возможных типов отмены регистров пользователей, например "инициировано клиентом", "регистрация просрочено" или "клиент перестает отвечать на запросы".</span><span class="sxs-lookup"><span data-stu-id="9d4fe-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="9d4fe-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-105">**Column**</span></span>|<span data-ttu-id="9d4fe-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-106">**Data Type**</span></span>|<span data-ttu-id="9d4fe-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-107">**Key/Index**</span></span>|<span data-ttu-id="9d4fe-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d4fe-109">**дерегистертипеид**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="9d4fe-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9d4fe-110">tinyint</span></span>  <br/> |<span data-ttu-id="9d4fe-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9d4fe-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9d4fe-112">**дерегистерреасон**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="9d4fe-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9d4fe-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9d4fe-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9d4fe-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9d4fe-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="9d4fe-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="9d4fe-116">1 — клиент инициировал отмену регистрации</span><span class="sxs-lookup"><span data-stu-id="9d4fe-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="9d4fe-117">2 — срок действия регистрации истек</span><span class="sxs-lookup"><span data-stu-id="9d4fe-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="9d4fe-118">3-Клиент аварийно завершил работу</span><span class="sxs-lookup"><span data-stu-id="9d4fe-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="9d4fe-119">4 — изменились атрибуты пользователя</span><span class="sxs-lookup"><span data-stu-id="9d4fe-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="9d4fe-120">5 — основной регистратор изменился</span><span class="sxs-lookup"><span data-stu-id="9d4fe-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="9d4fe-121">6 — устаревший клиент в режиме выживания</span><span class="sxs-lookup"><span data-stu-id="9d4fe-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

