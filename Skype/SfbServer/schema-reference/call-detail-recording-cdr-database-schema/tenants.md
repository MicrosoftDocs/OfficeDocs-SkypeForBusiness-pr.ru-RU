---
title: Таблица Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: В таблице клиентов представляет собой вспомогательную таблицу, в которой хранится список различных клиентов. Каждая запись в таблице представляет один клиент.
ms.openlocfilehash: 68050ce76cc41d3fd66931fbdc0b0d3168786bc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930208"
---
# <a name="tenants-table"></a><span data-ttu-id="abdc6-104">Таблица Tenants</span><span class="sxs-lookup"><span data-stu-id="abdc6-104">Tenants table</span></span>
 
<span data-ttu-id="abdc6-105">В таблице клиентов представляет собой вспомогательную таблицу, в которой хранится список различных клиентов.</span><span class="sxs-lookup"><span data-stu-id="abdc6-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="abdc6-106">Каждая запись в таблице представляет один клиент.</span><span class="sxs-lookup"><span data-stu-id="abdc6-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abdc6-107">В локальном развертывании CDR использует встроенный ИД клиента для указания другой тип проверки подлинности, такие как общедоступный служба обмена Мгновенными сообщениями, федеративными или анонимное подключение.</span><span class="sxs-lookup"><span data-stu-id="abdc6-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="abdc6-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="abdc6-108">**Column**</span></span>|<span data-ttu-id="abdc6-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="abdc6-109">**Data Type**</span></span>|<span data-ttu-id="abdc6-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="abdc6-110">**Key/Index**</span></span>|<span data-ttu-id="abdc6-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="abdc6-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="abdc6-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="abdc6-112">**TenantId**</span></span> <br/> |<span data-ttu-id="abdc6-113">целое</span><span class="sxs-lookup"><span data-stu-id="abdc6-113">int</span></span>  <br/> |<span data-ttu-id="abdc6-114">Primary</span><span class="sxs-lookup"><span data-stu-id="abdc6-114">Primary</span></span>  <br/> |<span data-ttu-id="abdc6-115">Уникальный номер, идентифицирующий ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="abdc6-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="abdc6-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="abdc6-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="abdc6-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="abdc6-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="abdc6-118">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="abdc6-118">Allowed values:</span></span> <br/>  <span data-ttu-id="abdc6-119">00000000-0000-0000-0000-000000000000-предприятия</span><span class="sxs-lookup"><span data-stu-id="abdc6-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="abdc6-120">00000000-0000-0000-0000-000000000001-федеративных</span><span class="sxs-lookup"><span data-stu-id="abdc6-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="abdc6-121">Очередей — - анонимный</span><span class="sxs-lookup"><span data-stu-id="abdc6-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="abdc6-122">00000000-0000-0000-0000-000000000003 — общедоступных служб обмена Мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="abdc6-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

