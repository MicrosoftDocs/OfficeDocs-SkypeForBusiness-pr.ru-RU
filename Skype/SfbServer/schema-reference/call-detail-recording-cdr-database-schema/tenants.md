---
title: Таблица Tenants
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: В таблице клиентов представляет собой вспомогательную таблицу, в которой хранится список различных клиентов. Каждая запись в таблице представляет один клиент.
ms.openlocfilehash: cf7d0271c9cacfd76079a80a7e5db63d669a8dfb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212770"
---
# <a name="tenants-table"></a><span data-ttu-id="b58f2-104">Таблица Tenants</span><span class="sxs-lookup"><span data-stu-id="b58f2-104">Tenants table</span></span>
 
<span data-ttu-id="b58f2-105">В таблице клиентов представляет собой вспомогательную таблицу, в которой хранится список различных клиентов.</span><span class="sxs-lookup"><span data-stu-id="b58f2-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="b58f2-106">Каждая запись в таблице представляет один клиент.</span><span class="sxs-lookup"><span data-stu-id="b58f2-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b58f2-107">В локальном развертывании CDR использует встроенный ИД клиента для указания другой тип проверки подлинности, такие как общедоступный служба обмена Мгновенными сообщениями, федеративными или анонимное подключение.</span><span class="sxs-lookup"><span data-stu-id="b58f2-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="b58f2-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b58f2-108">**Column**</span></span>|<span data-ttu-id="b58f2-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b58f2-109">**Data Type**</span></span>|<span data-ttu-id="b58f2-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="b58f2-110">**Key/Index**</span></span>|<span data-ttu-id="b58f2-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="b58f2-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b58f2-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="b58f2-112">**TenantId**</span></span> <br/> |<span data-ttu-id="b58f2-113">целое</span><span class="sxs-lookup"><span data-stu-id="b58f2-113">int</span></span>  <br/> |<span data-ttu-id="b58f2-114">Primary</span><span class="sxs-lookup"><span data-stu-id="b58f2-114">Primary</span></span>  <br/> |<span data-ttu-id="b58f2-115">Уникальный номер, идентифицирующий ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="b58f2-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="b58f2-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="b58f2-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="b58f2-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b58f2-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b58f2-118">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b58f2-118">Allowed values:</span></span> <br/>  <span data-ttu-id="b58f2-119">00000000-0000-0000-0000-000000000000-предприятия</span><span class="sxs-lookup"><span data-stu-id="b58f2-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="b58f2-120">00000000-0000-0000-0000-000000000001-федеративных</span><span class="sxs-lookup"><span data-stu-id="b58f2-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="b58f2-121">Очередей — - анонимный</span><span class="sxs-lookup"><span data-stu-id="b58f2-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="b58f2-122">00000000-0000-0000-0000-000000000003 — общедоступных служб обмена Мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b58f2-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

