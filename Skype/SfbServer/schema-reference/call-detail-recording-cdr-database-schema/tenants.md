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
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Таблица "клиенты" — это вспомогательная таблица, в которой хранится список различных клиентов. Каждая запись в таблице представляет собой один клиент.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295771"
---
# <a name="tenants-table"></a><span data-ttu-id="b9fce-104">Таблица Tenants</span><span class="sxs-lookup"><span data-stu-id="b9fce-104">Tenants table</span></span>
 
<span data-ttu-id="b9fce-105">Таблица "клиенты" — это вспомогательная таблица, в которой хранится список различных клиентов.</span><span class="sxs-lookup"><span data-stu-id="b9fce-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="b9fce-106">Каждая запись в таблице представляет собой один клиент.</span><span class="sxs-lookup"><span data-stu-id="b9fce-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9fce-107">В локальной среде CDR использует идентификатор клиента сборки для указания другого типа проверки подлинности, например общедоступной службы обмена мгновенными сообщениями, федеративного и анонимного.</span><span class="sxs-lookup"><span data-stu-id="b9fce-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="b9fce-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b9fce-108">**Column**</span></span>|<span data-ttu-id="b9fce-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b9fce-109">**Data Type**</span></span>|<span data-ttu-id="b9fce-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="b9fce-110">**Key/Index**</span></span>|<span data-ttu-id="b9fce-111">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="b9fce-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9fce-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="b9fce-112">**TenantId**</span></span> <br/> |<span data-ttu-id="b9fce-113">целое</span><span class="sxs-lookup"><span data-stu-id="b9fce-113">int</span></span>  <br/> |<span data-ttu-id="b9fce-114">Primary</span><span class="sxs-lookup"><span data-stu-id="b9fce-114">Primary</span></span>  <br/> |<span data-ttu-id="b9fce-115">Уникальный номер, идентифицирующий этот идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="b9fce-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="b9fce-116">**Тенанткэй**</span><span class="sxs-lookup"><span data-stu-id="b9fce-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="b9fce-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b9fce-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b9fce-118">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b9fce-118">Allowed values:</span></span> <br/>  <span data-ttu-id="b9fce-119">00000000-0000-0000-0000-000000000000 — корпоративный</span><span class="sxs-lookup"><span data-stu-id="b9fce-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="b9fce-120">00000000-0000-0000-0000-000000000001 — Федеративные</span><span class="sxs-lookup"><span data-stu-id="b9fce-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="b9fce-121">00000000-0000-0000-0000-000000000002 — анонимный</span><span class="sxs-lookup"><span data-stu-id="b9fce-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="b9fce-122">00000000-0000-0000-0000-000000000003-общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b9fce-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

