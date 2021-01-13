---
title: Представление UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800019"
---
# <a name="useragent-view"></a><span data-ttu-id="ba1df-104">Представление UserAgent</span><span class="sxs-lookup"><span data-stu-id="ba1df-104">UserAgent view</span></span>
 
<span data-ttu-id="ba1df-105">В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи.</span><span class="sxs-lookup"><span data-stu-id="ba1df-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="ba1df-106">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba1df-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ba1df-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ba1df-107">**Column**</span></span>|<span data-ttu-id="ba1df-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ba1df-108">**Data Type**</span></span>|<span data-ttu-id="ba1df-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="ba1df-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba1df-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="ba1df-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="ba1df-111">int</span><span class="sxs-lookup"><span data-stu-id="ba1df-111">int</span></span>  <br/> |<span data-ttu-id="ba1df-112">Уникальное число, идентифицирующее этот агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba1df-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="ba1df-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="ba1df-113">UserAgent</span></span>  <br/> |<span data-ttu-id="ba1df-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba1df-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba1df-115">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba1df-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="ba1df-116">UAType</span><span class="sxs-lookup"><span data-stu-id="ba1df-116">UAType</span></span>  <br/> |<span data-ttu-id="ba1df-117">smallint</span><span class="sxs-lookup"><span data-stu-id="ba1df-117">smallint</span></span>  <br/> |<span data-ttu-id="ba1df-118">Тип агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba1df-118">Type of user agent.</span></span> <span data-ttu-id="ba1df-119">Дополнительные сведения см. в таблице [UserAgent.](useragent.md)</span><span class="sxs-lookup"><span data-stu-id="ba1df-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="ba1df-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="ba1df-120">UACategory</span></span>  <br/> |<span data-ttu-id="ba1df-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="ba1df-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="ba1df-p104">Категория, к которой принадлежит агент пользователя. Например, агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="ba1df-p104">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

