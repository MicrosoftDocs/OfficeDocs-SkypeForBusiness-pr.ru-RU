---
title: Таблица Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Таблица "клиенты" — это вспомогательная таблица, в которой хранится список различных клиентов. Каждая запись в таблице представляет собой один клиент.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814857"
---
# <a name="tenants-table"></a><span data-ttu-id="abb35-104">Таблица Tenants</span><span class="sxs-lookup"><span data-stu-id="abb35-104">Tenants table</span></span>
 
<span data-ttu-id="abb35-105">Таблица "клиенты" — это вспомогательная таблица, в которой хранится список различных клиентов.</span><span class="sxs-lookup"><span data-stu-id="abb35-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="abb35-106">Каждая запись в таблице представляет собой один клиент.</span><span class="sxs-lookup"><span data-stu-id="abb35-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abb35-107">В локальной среде CDR использует идентификатор клиента сборки для указания другого типа проверки подлинности, например общедоступной службы обмена мгновенными сообщениями, федеративного и анонимного.</span><span class="sxs-lookup"><span data-stu-id="abb35-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="abb35-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="abb35-108">**Column**</span></span>|<span data-ttu-id="abb35-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="abb35-109">**Data Type**</span></span>|<span data-ttu-id="abb35-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="abb35-110">**Key/Index**</span></span>|<span data-ttu-id="abb35-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="abb35-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="abb35-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="abb35-112">**TenantId**</span></span> <br/> |<span data-ttu-id="abb35-113">целое</span><span class="sxs-lookup"><span data-stu-id="abb35-113">int</span></span>  <br/> |<span data-ttu-id="abb35-114">Primary</span><span class="sxs-lookup"><span data-stu-id="abb35-114">Primary</span></span>  <br/> |<span data-ttu-id="abb35-115">Уникальный номер, идентифицирующий этот идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="abb35-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="abb35-116">**тенанткэй**</span><span class="sxs-lookup"><span data-stu-id="abb35-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="abb35-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="abb35-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="abb35-118">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="abb35-118">Allowed values:</span></span> <br/>  <span data-ttu-id="abb35-119">00000000-0000-0000-0000-000000000000 — корпоративный</span><span class="sxs-lookup"><span data-stu-id="abb35-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="abb35-120">00000000-0000-0000-0000-000000000001 — Федеративные</span><span class="sxs-lookup"><span data-stu-id="abb35-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="abb35-121">00000000-0000-0000-0000-000000000002 — анонимный</span><span class="sxs-lookup"><span data-stu-id="abb35-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="abb35-122">00000000-0000-0000-0000-000000000003-общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="abb35-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

