---
title: Таблица DeRegisterType в Скайп для Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213195"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="95b88-103">Таблица DeRegisterType в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="95b88-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95b88-104">Таблица DeRegisterType — это статическая таблица, в которой хранится список возможных пользователя отмены регистрации типов, например «инициируется клиентом», «срок действия регистрации истек» или «клиент перестал отвечать».</span><span class="sxs-lookup"><span data-stu-id="95b88-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="95b88-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="95b88-105">**Column**</span></span>|<span data-ttu-id="95b88-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="95b88-106">**Data Type**</span></span>|<span data-ttu-id="95b88-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="95b88-107">**Key/Index**</span></span>|<span data-ttu-id="95b88-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="95b88-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95b88-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="95b88-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="95b88-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="95b88-110">tinyint</span></span>  <br/> |<span data-ttu-id="95b88-111">Primary</span><span class="sxs-lookup"><span data-stu-id="95b88-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="95b88-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="95b88-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="95b88-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="95b88-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="95b88-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="95b88-114">Allowed values:</span></span> <br/>  <span data-ttu-id="95b88-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="95b88-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="95b88-116">1 — Клиент инициировал отмену регистрации</span><span class="sxs-lookup"><span data-stu-id="95b88-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="95b88-117">2 — срок действия регистрации истек</span><span class="sxs-lookup"><span data-stu-id="95b88-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="95b88-118">3 — аварийное завершение клиента</span><span class="sxs-lookup"><span data-stu-id="95b88-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="95b88-119">4 — атрибуты пользователя изменены</span><span class="sxs-lookup"><span data-stu-id="95b88-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="95b88-120">5 — предпочтительный регистратор изменен</span><span class="sxs-lookup"><span data-stu-id="95b88-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="95b88-121">6 — Устаревший клиент в режиме сохранения</span><span class="sxs-lookup"><span data-stu-id="95b88-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

