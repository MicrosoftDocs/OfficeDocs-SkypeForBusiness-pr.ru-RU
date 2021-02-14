---
title: Таблица Pool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Во вспомогательной таблице Pool хранятся сведения о различных интерфейсных пулах. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815819"
---
# <a name="pool-table"></a><span data-ttu-id="48215-104">Таблица Pool</span><span class="sxs-lookup"><span data-stu-id="48215-104">Pool table</span></span>
 
<span data-ttu-id="48215-p102">Во вспомогательной таблице Pool хранятся сведения о различных интерфейсных пулах. Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="48215-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="48215-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="48215-107">**Column**</span></span>|<span data-ttu-id="48215-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="48215-108">**Data Type**</span></span>|<span data-ttu-id="48215-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="48215-109">**Key/Index**</span></span>|<span data-ttu-id="48215-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="48215-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48215-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="48215-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="48215-112">int</span><span class="sxs-lookup"><span data-stu-id="48215-112">int</span></span>  <br/> |<span data-ttu-id="48215-113">Primary</span><span class="sxs-lookup"><span data-stu-id="48215-113">Primary</span></span>  <br/> |<span data-ttu-id="48215-114">Уникальный номер, определяющий пул.</span><span class="sxs-lookup"><span data-stu-id="48215-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="48215-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="48215-115">**PoolName**</span></span> <br/> |<span data-ttu-id="48215-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="48215-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="48215-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="48215-117">Unique</span></span>  <br/> |<span data-ttu-id="48215-118">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="48215-118">Pool FQDN.</span></span>  <br/> |
   

