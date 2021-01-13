---
title: Представление ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813299"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="9404e-104">Представление ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="9404e-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="9404e-105">В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции.</span><span class="sxs-lookup"><span data-stu-id="9404e-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="9404e-106">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9404e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9404e-107">Представление ConferenceMessageCount содержит все столбцы в представлении [ConferenceSessionDetails,](conferencesessiondetails.md) а также столбцы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="9404e-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="9404e-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9404e-108">**Column**</span></span>|<span data-ttu-id="9404e-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9404e-109">**Data Type**</span></span>|<span data-ttu-id="9404e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="9404e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9404e-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="9404e-111">**UserUri**</span></span> <br/> |<span data-ttu-id="9404e-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9404e-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9404e-113">URI пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="9404e-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="9404e-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="9404e-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="9404e-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9404e-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9404e-116">Тип URI пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="9404e-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="9404e-117">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="9404e-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9404e-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="9404e-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="9404e-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9404e-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="9404e-120">Клиент пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="9404e-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="9404e-121">Дополнительные [сведения см. в](tenants.md) таблице Tenants.</span><span class="sxs-lookup"><span data-stu-id="9404e-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9404e-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="9404e-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="9404e-123">smallint</span><span class="sxs-lookup"><span data-stu-id="9404e-123">smallint</span></span>  <br/> |<span data-ttu-id="9404e-124">Количество сообщений, отправленных пользователем во время сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9404e-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

