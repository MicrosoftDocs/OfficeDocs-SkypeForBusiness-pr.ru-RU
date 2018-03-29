---
title: Таблица Tenants
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
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a><span data-ttu-id="941b1-104">Таблица Tenants</span><span class="sxs-lookup"><span data-stu-id="941b1-104">Tenants table</span></span>
 
<span data-ttu-id="941b1-105">В таблице клиентов представляет собой вспомогательную таблицу, в которой хранится список различных клиентов.</span><span class="sxs-lookup"><span data-stu-id="941b1-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="941b1-106">Каждая запись в таблице представляет один клиент.</span><span class="sxs-lookup"><span data-stu-id="941b1-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="941b1-107">В локальном развертывании CDR использует встроенный ИД клиента для указания другой тип проверки подлинности, такие как общедоступный служба обмена Мгновенными сообщениями, федеративными или анонимное подключение.</span><span class="sxs-lookup"><span data-stu-id="941b1-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="941b1-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="941b1-108">**Column**</span></span>|<span data-ttu-id="941b1-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="941b1-109">**Data Type**</span></span>|<span data-ttu-id="941b1-110">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="941b1-110">**Key/Index**</span></span>|<span data-ttu-id="941b1-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="941b1-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="941b1-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="941b1-112">**TenantId**</span></span> <br/> |<span data-ttu-id="941b1-113">целое</span><span class="sxs-lookup"><span data-stu-id="941b1-113">int</span></span>  <br/> |<span data-ttu-id="941b1-114">Primary</span><span class="sxs-lookup"><span data-stu-id="941b1-114">Primary</span></span>  <br/> |<span data-ttu-id="941b1-115">Уникальный номер, идентифицирующий ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="941b1-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="941b1-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="941b1-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="941b1-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="941b1-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="941b1-118">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="941b1-118">Allowed values:</span></span> <br/>  <span data-ttu-id="941b1-119">00000000-0000-0000-0000-000000000000-предприятия</span><span class="sxs-lookup"><span data-stu-id="941b1-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="941b1-120">00000000-0000-0000-0000-000000000001-федеративных</span><span class="sxs-lookup"><span data-stu-id="941b1-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="941b1-121">Очередей — - анонимный</span><span class="sxs-lookup"><span data-stu-id="941b1-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="941b1-122">00000000-0000-0000-0000-000000000003 — общедоступных служб обмена Мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="941b1-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

