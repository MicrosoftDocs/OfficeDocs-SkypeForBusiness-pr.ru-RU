---
title: Представление ConferenceMessageCount
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Представление ConferenceMessageCount содержит сведения о количества сообщений — пользователя к конференции. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: f0206145217f63e4530d2eac39c7c6533dcf154e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="6151d-104">Представление ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="6151d-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="6151d-105">Представление ConferenceMessageCount содержит сведения о количества сообщений — пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="6151d-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="6151d-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6151d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6151d-107">Представление ConferenceMessageCount содержит все столбцы [ConferenceSessionDetails view](conferencesessiondetails.md) в дополнение к этому столбцов, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="6151d-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="6151d-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6151d-108">**Column**</span></span>|<span data-ttu-id="6151d-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6151d-109">**Data Type**</span></span>|<span data-ttu-id="6151d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6151d-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6151d-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="6151d-111">**UserUri**</span></span> <br/> |<span data-ttu-id="6151d-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6151d-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6151d-113">URI пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="6151d-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="6151d-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="6151d-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="6151d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6151d-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6151d-116">Тип URI пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="6151d-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="6151d-117">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="6151d-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6151d-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="6151d-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="6151d-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6151d-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="6151d-120">Клиент пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="6151d-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="6151d-121">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="6151d-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6151d-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="6151d-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="6151d-123">smallint</span><span class="sxs-lookup"><span data-stu-id="6151d-123">smallint</span></span>  <br/> |<span data-ttu-id="6151d-124">Число сообщений, отправленных пользователем во время сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="6151d-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

