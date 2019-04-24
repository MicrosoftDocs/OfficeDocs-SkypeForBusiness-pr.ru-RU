---
title: Представление UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Представление UserAgent хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212069"
---
# <a name="useragent-view"></a><span data-ttu-id="8e6f4-104">Представление UserAgent</span><span class="sxs-lookup"><span data-stu-id="8e6f4-104">UserAgent view</span></span>
 
<span data-ttu-id="8e6f4-105">Представление UserAgent хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="8e6f4-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8e6f4-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8e6f4-107">**Column**</span></span>|<span data-ttu-id="8e6f4-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8e6f4-108">**Data Type**</span></span>|<span data-ttu-id="8e6f4-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8e6f4-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e6f4-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="8e6f4-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="8e6f4-111">целое</span><span class="sxs-lookup"><span data-stu-id="8e6f4-111">int</span></span>  <br/> |<span data-ttu-id="8e6f4-112">Уникальный номер, идентифицирующий этот агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="8e6f4-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="8e6f4-113">UserAgent</span></span>  <br/> |<span data-ttu-id="8e6f4-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e6f4-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8e6f4-115">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="8e6f4-116">UAType</span><span class="sxs-lookup"><span data-stu-id="8e6f4-116">UAType</span></span>  <br/> |<span data-ttu-id="8e6f4-117">smallint</span><span class="sxs-lookup"><span data-stu-id="8e6f4-117">smallint</span></span>  <br/> |<span data-ttu-id="8e6f4-118">Тип агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-118">Type of user agent.</span></span> <span data-ttu-id="8e6f4-119">В разделе [Таблица UserAgent](useragent.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="8e6f4-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="8e6f4-120">UACategory</span></span>  <br/> |<span data-ttu-id="8e6f4-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="8e6f4-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="8e6f4-122">Категория, к которой принадлежит агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="8e6f4-123">Например агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="8e6f4-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

