---
title: Таблица Phones
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица phones является вспомогательной таблицей. Каждая запись в таблице хранит информацию об одном номере телефона, который участвует в звонках по протоколу VoIP с записями в базе данных.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815007"
---
# <a name="phones-table"></a><span data-ttu-id="a3721-104">Таблица Phones</span><span class="sxs-lookup"><span data-stu-id="a3721-104">Phones table</span></span>
 
<span data-ttu-id="a3721-105">Таблица phones является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="a3721-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="a3721-106">Каждая запись в таблице хранит информацию об одном номере телефона, который участвует в звонках по протоколу VoIP с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a3721-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="a3721-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a3721-107">**Column**</span></span>|<span data-ttu-id="a3721-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a3721-108">**Data Type**</span></span>|<span data-ttu-id="a3721-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a3721-109">**Key/Index**</span></span>|<span data-ttu-id="a3721-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a3721-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3721-111">**фонеид**</span><span class="sxs-lookup"><span data-stu-id="a3721-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="a3721-112">целое</span><span class="sxs-lookup"><span data-stu-id="a3721-112">int</span></span>  <br/> |<span data-ttu-id="a3721-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a3721-113">Primary</span></span>  <br/> |<span data-ttu-id="a3721-114">Уникальный номер, идентифицирующий этот телефон.</span><span class="sxs-lookup"><span data-stu-id="a3721-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="a3721-115">**фонеури**</span><span class="sxs-lookup"><span data-stu-id="a3721-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="a3721-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a3721-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="a3721-117">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="a3721-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="a3721-118">**некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="a3721-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="a3721-119">Датой</span><span class="sxs-lookup"><span data-stu-id="a3721-119">dateTime</span></span>  <br/> ||<span data-ttu-id="a3721-120">Метка времени (только для внутреннего использования).</span><span class="sxs-lookup"><span data-stu-id="a3721-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="a3721-121">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3721-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

