---
title: Таблица Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Таблица Pool — это вспомогательная таблица, в которой хранятся сведения о различных пулах интерфейсов переднего плана. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807407"
---
# <a name="pool-table"></a><span data-ttu-id="0459c-104">Таблица Pool</span><span class="sxs-lookup"><span data-stu-id="0459c-104">Pool table</span></span>
 
<span data-ttu-id="0459c-105">Таблица Pool — это вспомогательная таблица, в которой хранятся сведения о различных пулах интерфейсов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0459c-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="0459c-106">Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="0459c-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="0459c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0459c-107">**Column**</span></span>|<span data-ttu-id="0459c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="0459c-108">**Data Type**</span></span>|<span data-ttu-id="0459c-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="0459c-109">**Key/Index**</span></span>|<span data-ttu-id="0459c-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="0459c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0459c-111">**пулкэй**</span><span class="sxs-lookup"><span data-stu-id="0459c-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="0459c-112">целое</span><span class="sxs-lookup"><span data-stu-id="0459c-112">int</span></span>  <br/> |<span data-ttu-id="0459c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0459c-113">Primary</span></span>  <br/> |<span data-ttu-id="0459c-114">Уникальный номер, идентифицирующий этот пул.</span><span class="sxs-lookup"><span data-stu-id="0459c-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="0459c-115">**пулнаме**</span><span class="sxs-lookup"><span data-stu-id="0459c-115">**PoolName**</span></span> <br/> |<span data-ttu-id="0459c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0459c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0459c-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="0459c-117">Unique</span></span>  <br/> |<span data-ttu-id="0459c-118">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="0459c-118">Pool FQDN.</span></span>  <br/> |
   

