---
title: Представление Mcus
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
ms.assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
description: В представлении Mcus хранятся сведения о блоках MCU, которые участвовали в сеансах конференц-связи. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 3b16505337c241f08b1da99ca2e9e7f8a17a4eaa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821469"
---
# <a name="mcus-view"></a><span data-ttu-id="9f18c-104">Представление Mcus</span><span class="sxs-lookup"><span data-stu-id="9f18c-104">Mcus view</span></span>
 
<span data-ttu-id="9f18c-105">В представлении Mcus хранятся сведения о блоках MCU, которые участвовали в сеансах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9f18c-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="9f18c-106">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f18c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9f18c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9f18c-107">**Column**</span></span>|<span data-ttu-id="9f18c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9f18c-108">**Data Type**</span></span>|<span data-ttu-id="9f18c-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="9f18c-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9f18c-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="9f18c-110">**McuId**</span></span> <br/> |<span data-ttu-id="9f18c-111">int</span><span class="sxs-lookup"><span data-stu-id="9f18c-111">int</span></span>  <br/> |<span data-ttu-id="9f18c-112">Уникальный номер, идентифицирующий MCU.</span><span class="sxs-lookup"><span data-stu-id="9f18c-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="9f18c-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="9f18c-113">**McuUri**</span></span> <br/> |<span data-ttu-id="9f18c-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9f18c-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9f18c-115">URI блока MCU.</span><span class="sxs-lookup"><span data-stu-id="9f18c-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="9f18c-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="9f18c-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="9f18c-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f18c-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9f18c-118">Тип URI блока MCU.</span><span class="sxs-lookup"><span data-stu-id="9f18c-118">Type of MCU URI.</span></span> <span data-ttu-id="9f18c-119">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="9f18c-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

