---
title: Таблица DeRegisterType в Skype для бизнеса Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Таблица DeRegisterType — это статическая таблица, в которую хранится список возможных типов регистрации пользователей, таких как "инициализированный клиент", "срок действия регистрации истек" или "клиент перестал отвечать".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816079"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="27f9e-103">Таблица DeRegisterType в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="27f9e-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="27f9e-104">Таблица DeRegisterType — это статическая таблица, в которую хранится список возможных типов регистрации пользователей, таких как "инициирован клиент", "срок действия регистрации истек" или "клиент перестал отвечать".</span><span class="sxs-lookup"><span data-stu-id="27f9e-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="27f9e-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="27f9e-105">**Column**</span></span>|<span data-ttu-id="27f9e-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="27f9e-106">**Data Type**</span></span>|<span data-ttu-id="27f9e-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="27f9e-107">**Key/Index**</span></span>|<span data-ttu-id="27f9e-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="27f9e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27f9e-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="27f9e-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="27f9e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="27f9e-110">tinyint</span></span>  <br/> |<span data-ttu-id="27f9e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="27f9e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="27f9e-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="27f9e-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="27f9e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="27f9e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="27f9e-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="27f9e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="27f9e-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="27f9e-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="27f9e-116">1 — клиент инициировал отмену регистрации</span><span class="sxs-lookup"><span data-stu-id="27f9e-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="27f9e-117">2 — срок действия регистрации истек</span><span class="sxs-lookup"><span data-stu-id="27f9e-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="27f9e-118">3 — сбой клиента</span><span class="sxs-lookup"><span data-stu-id="27f9e-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="27f9e-119">4 — атрибуты пользователя изменены</span><span class="sxs-lookup"><span data-stu-id="27f9e-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="27f9e-120">5 — предпочтительный регистратор изменен</span><span class="sxs-lookup"><span data-stu-id="27f9e-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="27f9e-121">6 — устаревший клиент в режиме сохранения</span><span class="sxs-lookup"><span data-stu-id="27f9e-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

