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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица phones является вспомогательной таблицей. Каждая запись в таблице хранит информацию об одном номере телефона, который участвует в звонках по протоколу VoIP с записями в базе данных.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295946"
---
# <a name="phones-table"></a><span data-ttu-id="6402b-104">Таблица Phones</span><span class="sxs-lookup"><span data-stu-id="6402b-104">Phones table</span></span>
 
<span data-ttu-id="6402b-105">Таблица phones является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="6402b-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="6402b-106">Каждая запись в таблице хранит информацию об одном номере телефона, который участвует в звонках по протоколу VoIP с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="6402b-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="6402b-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6402b-107">**Column**</span></span>|<span data-ttu-id="6402b-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6402b-108">**Data Type**</span></span>|<span data-ttu-id="6402b-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="6402b-109">**Key/Index**</span></span>|<span data-ttu-id="6402b-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6402b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6402b-111">**Фонеид**</span><span class="sxs-lookup"><span data-stu-id="6402b-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="6402b-112">целое</span><span class="sxs-lookup"><span data-stu-id="6402b-112">int</span></span>  <br/> |<span data-ttu-id="6402b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6402b-113">Primary</span></span>  <br/> |<span data-ttu-id="6402b-114">Уникальный номер, идентифицирующий этот телефон.</span><span class="sxs-lookup"><span data-stu-id="6402b-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="6402b-115">**Фонеури**</span><span class="sxs-lookup"><span data-stu-id="6402b-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="6402b-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6402b-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="6402b-117">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="6402b-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="6402b-118">**Некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="6402b-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6402b-119">Датой</span><span class="sxs-lookup"><span data-stu-id="6402b-119">dateTime</span></span>  <br/> ||<span data-ttu-id="6402b-120">Метка времени (только для внутреннего использования).</span><span class="sxs-lookup"><span data-stu-id="6402b-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="6402b-121">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6402b-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

