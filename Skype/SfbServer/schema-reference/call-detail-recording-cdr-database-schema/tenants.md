---
title: Таблица Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Таблица клиентов является вспомогательной таблицей, в которой хранится список различных клиентов. Каждая запись в таблице представляет одного клиента.
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831719"
---
# <a name="tenants-table"></a><span data-ttu-id="81404-104">Таблица Tenants</span><span class="sxs-lookup"><span data-stu-id="81404-104">Tenants table</span></span>
 
<span data-ttu-id="81404-p102">Таблица клиентов является вспомогательной таблицей, в которой хранится список различных клиентов. Каждая запись в таблице представляет одного клиента.</span><span class="sxs-lookup"><span data-stu-id="81404-p102">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81404-107">В локальном развертывании CDR использует встроенный ИД клиента, чтобы показать различные типы проверки подлинности, такие как общедоступное подключение для обмена мгновенными сообщениями, федеративное подключение или анонимное подключение.</span><span class="sxs-lookup"><span data-stu-id="81404-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="81404-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="81404-108">**Column**</span></span>|<span data-ttu-id="81404-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="81404-109">**Data Type**</span></span>|<span data-ttu-id="81404-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="81404-110">**Key/Index**</span></span>|<span data-ttu-id="81404-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="81404-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81404-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="81404-112">**TenantId**</span></span> <br/> |<span data-ttu-id="81404-113">int</span><span class="sxs-lookup"><span data-stu-id="81404-113">int</span></span>  <br/> |<span data-ttu-id="81404-114">Primary</span><span class="sxs-lookup"><span data-stu-id="81404-114">Primary</span></span>  <br/> |<span data-ttu-id="81404-115">Уникальное число, определяющее ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="81404-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="81404-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="81404-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="81404-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81404-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="81404-118">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="81404-118">Allowed values:</span></span> <br/>  <span data-ttu-id="81404-119">00000000-0000-0000-0000-00000000000000000 - Enterprise</span><span class="sxs-lookup"><span data-stu-id="81404-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="81404-120">00000000-0000-0000-0000-000000000001 федера</span><span class="sxs-lookup"><span data-stu-id="81404-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="81404-121">00000000-0000-0000-0000-0000000000002 — анонимный</span><span class="sxs-lookup"><span data-stu-id="81404-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="81404-122">00000000-0000-0000-0000-000000000003 — подключение к общедоступным службе мгновенных услуг</span><span class="sxs-lookup"><span data-stu-id="81404-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

