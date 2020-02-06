---
title: Таблица Усерстатистикс
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица Усерстатистикс является вспомогательной таблицей. Каждая запись в таблице содержит сведения об использовании системы конкретным пользователем. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814797"
---
# <a name="userstatistics-table"></a><span data-ttu-id="4a348-105">Таблица Усерстатистикс</span><span class="sxs-lookup"><span data-stu-id="4a348-105">UserStatistics table</span></span>
 
<span data-ttu-id="4a348-106">Таблица Усерстатистикс является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="4a348-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="4a348-107">Каждая запись в таблице содержит сведения об использовании системы конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="4a348-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="4a348-108">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a348-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4a348-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4a348-109">**Column**</span></span>|<span data-ttu-id="4a348-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4a348-110">**Data Type**</span></span>|<span data-ttu-id="4a348-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4a348-111">**Key/Index**</span></span>|<span data-ttu-id="4a348-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4a348-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a348-113">**Идентификатора пользователя**</span><span class="sxs-lookup"><span data-stu-id="4a348-113">**UserId**</span></span> <br/> |<span data-ttu-id="4a348-114">целое</span><span class="sxs-lookup"><span data-stu-id="4a348-114">int</span></span>  <br/> |<span data-ttu-id="4a348-115">Primary</span><span class="sxs-lookup"><span data-stu-id="4a348-115">Primary</span></span>  <br/> |<span data-ttu-id="4a348-116">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a348-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4a348-117">**ластлогинтиме**</span><span class="sxs-lookup"><span data-stu-id="4a348-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="4a348-118">datetime</span><span class="sxs-lookup"><span data-stu-id="4a348-118">datetime</span></span>  <br/> ||<span data-ttu-id="4a348-119">Время последнего входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="4a348-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="4a348-120">**ластконфорганизедтиме**</span><span class="sxs-lookup"><span data-stu-id="4a348-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="4a348-121">datetime</span><span class="sxs-lookup"><span data-stu-id="4a348-121">datetime</span></span>  <br/> ||<span data-ttu-id="4a348-122">Последний раз, когда пользователь организует конференцию.</span><span class="sxs-lookup"><span data-stu-id="4a348-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="4a348-123">**ласткаллорганизеркаллфаилуретиме**</span><span class="sxs-lookup"><span data-stu-id="4a348-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="4a348-124">datetime</span><span class="sxs-lookup"><span data-stu-id="4a348-124">datetime</span></span>  <br/> ||<span data-ttu-id="4a348-125">Последнее время, когда пользователь попытался вызвать сбой звонка.</span><span class="sxs-lookup"><span data-stu-id="4a348-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="4a348-126">**ластконфорганизеркаллфаилуретиме**</span><span class="sxs-lookup"><span data-stu-id="4a348-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="4a348-127">datetime</span><span class="sxs-lookup"><span data-stu-id="4a348-127">datetime</span></span>  <br/> ||<span data-ttu-id="4a348-128">Последний раз, когда пользователь попытался вызвать сбой в организаторе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="4a348-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

