---
title: Таблица Phones
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица Phones является вспомогательной. В каждой записи таблицы хранится информация об одном телефонном номере, который участвует в вызовах VoIP, в базе данных которых есть записи.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823269"
---
# <a name="phones-table"></a><span data-ttu-id="2954f-104">Таблица Phones</span><span class="sxs-lookup"><span data-stu-id="2954f-104">Phones table</span></span>
 
<span data-ttu-id="2954f-105">Таблица Phones является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="2954f-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="2954f-106">В каждой записи таблицы хранится информация об одном телефонном номере, задействованном в вызовах VoIP, которые имеют записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2954f-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="2954f-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2954f-107">**Column**</span></span>|<span data-ttu-id="2954f-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2954f-108">**Data Type**</span></span>|<span data-ttu-id="2954f-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="2954f-109">**Key/Index**</span></span>|<span data-ttu-id="2954f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="2954f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2954f-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="2954f-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="2954f-112">int</span><span class="sxs-lookup"><span data-stu-id="2954f-112">int</span></span>  <br/> |<span data-ttu-id="2954f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2954f-113">Primary</span></span>  <br/> |<span data-ttu-id="2954f-114">Уникальный номер, идентифицирующий этот телефон.</span><span class="sxs-lookup"><span data-stu-id="2954f-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="2954f-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="2954f-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="2954f-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="2954f-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="2954f-117">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="2954f-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="2954f-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2954f-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2954f-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="2954f-119">dateTime</span></span>  <br/> ||<span data-ttu-id="2954f-120">Отметка времени (только для внутреннего использования).</span><span class="sxs-lookup"><span data-stu-id="2954f-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="2954f-121">Это поле было впервые введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2954f-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

