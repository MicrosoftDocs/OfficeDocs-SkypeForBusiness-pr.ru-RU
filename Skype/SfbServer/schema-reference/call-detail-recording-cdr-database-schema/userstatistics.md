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
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица Усерстатистикс является вспомогательной таблицей. Каждая запись в таблице содержит сведения об использовании системы конкретным пользователем. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295694"
---
# <a name="userstatistics-table"></a><span data-ttu-id="7bf07-105">Таблица Усерстатистикс</span><span class="sxs-lookup"><span data-stu-id="7bf07-105">UserStatistics table</span></span>
 
<span data-ttu-id="7bf07-106">Таблица Усерстатистикс является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="7bf07-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="7bf07-107">Каждая запись в таблице содержит сведения об использовании системы конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="7bf07-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="7bf07-108">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7bf07-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7bf07-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7bf07-109">**Column**</span></span>|<span data-ttu-id="7bf07-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7bf07-110">**Data Type**</span></span>|<span data-ttu-id="7bf07-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7bf07-111">**Key/Index**</span></span>|<span data-ttu-id="7bf07-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7bf07-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7bf07-113">**Идентификатора пользователя**</span><span class="sxs-lookup"><span data-stu-id="7bf07-113">**UserId**</span></span> <br/> |<span data-ttu-id="7bf07-114">целое</span><span class="sxs-lookup"><span data-stu-id="7bf07-114">int</span></span>  <br/> |<span data-ttu-id="7bf07-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7bf07-115">Primary</span></span>  <br/> |<span data-ttu-id="7bf07-116">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="7bf07-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="7bf07-117">**Ластлогинтиме**</span><span class="sxs-lookup"><span data-stu-id="7bf07-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="7bf07-118">datetime</span><span class="sxs-lookup"><span data-stu-id="7bf07-118">datetime</span></span>  <br/> ||<span data-ttu-id="7bf07-119">Время последнего входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="7bf07-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="7bf07-120">**Ластконфорганизедтиме**</span><span class="sxs-lookup"><span data-stu-id="7bf07-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="7bf07-121">datetime</span><span class="sxs-lookup"><span data-stu-id="7bf07-121">datetime</span></span>  <br/> ||<span data-ttu-id="7bf07-122">Последний раз, когда пользователь организует конференцию.</span><span class="sxs-lookup"><span data-stu-id="7bf07-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="7bf07-123">**Ласткаллорганизеркаллфаилуретиме**</span><span class="sxs-lookup"><span data-stu-id="7bf07-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="7bf07-124">datetime</span><span class="sxs-lookup"><span data-stu-id="7bf07-124">datetime</span></span>  <br/> ||<span data-ttu-id="7bf07-125">Последнее время, когда пользователь попытался вызвать сбой звонка.</span><span class="sxs-lookup"><span data-stu-id="7bf07-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="7bf07-126">**Ластконфорганизеркаллфаилуретиме**</span><span class="sxs-lookup"><span data-stu-id="7bf07-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="7bf07-127">datetime</span><span class="sxs-lookup"><span data-stu-id="7bf07-127">datetime</span></span>  <br/> ||<span data-ttu-id="7bf07-128">Последний раз, когда пользователь попытался вызвать сбой в организаторе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="7bf07-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

