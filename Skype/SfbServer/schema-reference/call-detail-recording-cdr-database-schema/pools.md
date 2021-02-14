---
title: Таблица Pools
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
ms.assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
description: Таблица Pools — это вспомогательная таблица, в которую хранится информация о различных пулах. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: bb0b794c38617d20b9a718fc9a44ec17c3a9ec66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823219"
---
# <a name="pools-table"></a><span data-ttu-id="e8a4a-104">Таблица Pools</span><span class="sxs-lookup"><span data-stu-id="e8a4a-104">Pools table</span></span>
 
<span data-ttu-id="e8a4a-105">Таблица Pools — это вспомогательная таблица, в которую хранится информация о различных пулах.</span><span class="sxs-lookup"><span data-stu-id="e8a4a-105">The Pools table is a supporting table that stores information about the various pool.</span></span> <span data-ttu-id="e8a4a-106">Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="e8a4a-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="e8a4a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e8a4a-107">**Column**</span></span>|<span data-ttu-id="e8a4a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e8a4a-108">**Data Type**</span></span>|<span data-ttu-id="e8a4a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="e8a4a-109">**Key/Index**</span></span>|<span data-ttu-id="e8a4a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e8a4a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8a4a-111">**PoolId**</span><span class="sxs-lookup"><span data-stu-id="e8a4a-111">**PoolId**</span></span> <br/> |<span data-ttu-id="e8a4a-112">int</span><span class="sxs-lookup"><span data-stu-id="e8a4a-112">int</span></span>  <br/> |<span data-ttu-id="e8a4a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e8a4a-113">Primary</span></span>  <br/> |<span data-ttu-id="e8a4a-114">Уникальный номер, определяющий пул.</span><span class="sxs-lookup"><span data-stu-id="e8a4a-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="e8a4a-115">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="e8a4a-115">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="e8a4a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e8a4a-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="e8a4a-117">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="e8a4a-117">Pool FQDN.</span></span>  <br/> |
   

