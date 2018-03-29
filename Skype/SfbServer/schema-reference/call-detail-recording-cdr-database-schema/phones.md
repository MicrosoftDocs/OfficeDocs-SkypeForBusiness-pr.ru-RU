---
title: Таблица Phones
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
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a><span data-ttu-id="46664-104">Таблица Phones</span><span class="sxs-lookup"><span data-stu-id="46664-104">Phones table</span></span>
 
<span data-ttu-id="46664-105">Таблица Phones представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="46664-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="46664-106">Каждая запись в таблице хранятся сведения о один телефонный номер, участвующих в вызовах VoIP с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="46664-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="46664-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="46664-107">**Column**</span></span>|<span data-ttu-id="46664-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="46664-108">**Data Type**</span></span>|<span data-ttu-id="46664-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="46664-109">**Key/Index**</span></span>|<span data-ttu-id="46664-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="46664-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46664-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="46664-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="46664-112">целое</span><span class="sxs-lookup"><span data-stu-id="46664-112">int</span></span>  <br/> |<span data-ttu-id="46664-113">Primary</span><span class="sxs-lookup"><span data-stu-id="46664-113">Primary</span></span>  <br/> |<span data-ttu-id="46664-114">Уникальный номер, идентифицирующий телефон.</span><span class="sxs-lookup"><span data-stu-id="46664-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="46664-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="46664-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="46664-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="46664-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="46664-117">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="46664-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="46664-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="46664-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="46664-119">даты и времени</span><span class="sxs-lookup"><span data-stu-id="46664-119">dateTime</span></span>  <br/> ||<span data-ttu-id="46664-120">Метка времени (только для внутреннего использования).</span><span class="sxs-lookup"><span data-stu-id="46664-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="46664-121">В этом поле было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46664-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

