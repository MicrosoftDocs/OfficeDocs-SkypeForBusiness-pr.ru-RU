---
title: Представление "UserAgent"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294609"
---
# <a name="useragent-view"></a><span data-ttu-id="5a8b0-104">Представление "UserAgent"</span><span class="sxs-lookup"><span data-stu-id="5a8b0-104">UserAgent view</span></span>
 
<span data-ttu-id="5a8b0-105">В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5a8b0-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="5a8b0-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a8b0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5a8b0-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5a8b0-107">**Column**</span></span>|<span data-ttu-id="5a8b0-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5a8b0-108">**Data Type**</span></span>|<span data-ttu-id="5a8b0-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="5a8b0-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a8b0-110">Усераженткэй</span><span class="sxs-lookup"><span data-stu-id="5a8b0-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="5a8b0-111">целое</span><span class="sxs-lookup"><span data-stu-id="5a8b0-111">int</span></span>  <br/> |<span data-ttu-id="5a8b0-112">Уникальный номер, идентифицирующий агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a8b0-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="5a8b0-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="5a8b0-113">UserAgent</span></span>  <br/> |<span data-ttu-id="5a8b0-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5a8b0-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5a8b0-115">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a8b0-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="5a8b0-116">Уатипе</span><span class="sxs-lookup"><span data-stu-id="5a8b0-116">UAType</span></span>  <br/> |<span data-ttu-id="5a8b0-117">smallint</span><span class="sxs-lookup"><span data-stu-id="5a8b0-117">smallint</span></span>  <br/> |<span data-ttu-id="5a8b0-118">Тип агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a8b0-118">Type of user agent.</span></span> <span data-ttu-id="5a8b0-119">Дополнительные сведения приведены в [таблице UserAgent](useragent.md) .</span><span class="sxs-lookup"><span data-stu-id="5a8b0-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="5a8b0-120">Уакатегори</span><span class="sxs-lookup"><span data-stu-id="5a8b0-120">UACategory</span></span>  <br/> |<span data-ttu-id="5a8b0-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5a8b0-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="5a8b0-122">Категория, к которой принадлежит агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a8b0-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="5a8b0-123">Например, агент пользователя КонференЦинг_аттендант_ 1.0 принадлежит к Уакатегори Каа.</span><span class="sxs-lookup"><span data-stu-id="5a8b0-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

