---
title: Таблица DeRegisterType в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Таблица DeRegisterType — это статическая таблица, в которой хранится список возможных пользователя отмены регистрации типов, например «инициируется клиентом», «срок действия регистрации истек» или «клиент перестал отвечать».
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="962b9-103">Таблица DeRegisterType в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="962b9-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="962b9-104">Таблица DeRegisterType — это статическая таблица, в которой хранится список возможных пользователя отмены регистрации типов, например «инициируется клиентом», «срок действия регистрации истек» или «клиент перестал отвечать».</span><span class="sxs-lookup"><span data-stu-id="962b9-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="962b9-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="962b9-105">**Column**</span></span>|<span data-ttu-id="962b9-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="962b9-106">**Data Type**</span></span>|<span data-ttu-id="962b9-107">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="962b9-107">**Key/Index**</span></span>|<span data-ttu-id="962b9-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="962b9-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="962b9-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="962b9-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="962b9-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="962b9-110">tinyint</span></span>  <br/> |<span data-ttu-id="962b9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="962b9-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="962b9-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="962b9-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="962b9-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="962b9-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="962b9-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="962b9-114">Allowed values:</span></span> <br/>  <span data-ttu-id="962b9-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="962b9-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="962b9-116">1 — Клиент инициировал отмену регистрации</span><span class="sxs-lookup"><span data-stu-id="962b9-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="962b9-117">2 — срок действия регистрации истек</span><span class="sxs-lookup"><span data-stu-id="962b9-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="962b9-118">3 — аварийное завершение клиента</span><span class="sxs-lookup"><span data-stu-id="962b9-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="962b9-119">4 — атрибуты пользователя изменены</span><span class="sxs-lookup"><span data-stu-id="962b9-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="962b9-120">5 — предпочтительный регистратор изменен</span><span class="sxs-lookup"><span data-stu-id="962b9-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="962b9-121">6 — Устаревший клиент в режиме сохранения</span><span class="sxs-lookup"><span data-stu-id="962b9-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

