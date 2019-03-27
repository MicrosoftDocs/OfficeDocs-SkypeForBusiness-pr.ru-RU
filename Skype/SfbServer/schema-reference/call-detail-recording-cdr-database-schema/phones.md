---
title: Таблица Phones
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица Phones представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о один телефонный номер, участвующих в вызовах VoIP с записями в базе данных.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894644"
---
# <a name="phones-table"></a><span data-ttu-id="5bea9-104">Таблица Phones</span><span class="sxs-lookup"><span data-stu-id="5bea9-104">Phones table</span></span>
 
<span data-ttu-id="5bea9-105">Таблица Phones представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="5bea9-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="5bea9-106">Каждая запись в таблице хранятся сведения о один телефонный номер, участвующих в вызовах VoIP с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5bea9-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="5bea9-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5bea9-107">**Column**</span></span>|<span data-ttu-id="5bea9-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5bea9-108">**Data Type**</span></span>|<span data-ttu-id="5bea9-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="5bea9-109">**Key/Index**</span></span>|<span data-ttu-id="5bea9-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="5bea9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5bea9-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="5bea9-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="5bea9-112">целое</span><span class="sxs-lookup"><span data-stu-id="5bea9-112">int</span></span>  <br/> |<span data-ttu-id="5bea9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5bea9-113">Primary</span></span>  <br/> |<span data-ttu-id="5bea9-114">Уникальный номер, идентифицирующий телефон.</span><span class="sxs-lookup"><span data-stu-id="5bea9-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="5bea9-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="5bea9-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="5bea9-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="5bea9-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="5bea9-117">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="5bea9-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="5bea9-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5bea9-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5bea9-119">даты и времени</span><span class="sxs-lookup"><span data-stu-id="5bea9-119">dateTime</span></span>  <br/> ||<span data-ttu-id="5bea9-120">Метка времени (только для внутреннего использования).</span><span class="sxs-lookup"><span data-stu-id="5bea9-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="5bea9-121">В этом поле было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bea9-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

