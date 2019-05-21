---
title: Представление Конференцемессажекаунт
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: В представлении Конференцемессажекаунт хранятся сведения о количестве сообщений, отправленных пользователем на конференцию. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296492"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="3104f-104">Представление Конференцемессажекаунт</span><span class="sxs-lookup"><span data-stu-id="3104f-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="3104f-105">В представлении Конференцемессажекаунт хранятся сведения о количестве сообщений, отправленных пользователем на конференцию.</span><span class="sxs-lookup"><span data-stu-id="3104f-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="3104f-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3104f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3104f-107">В представлении Конференцемессажекаунт содержатся все столбцы в [представлении "конференцесессиондетаилс](conferencesessiondetails.md) " в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="3104f-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="3104f-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3104f-108">**Column**</span></span>|<span data-ttu-id="3104f-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3104f-109">**Data Type**</span></span>|<span data-ttu-id="3104f-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="3104f-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3104f-111">**Усерури**</span><span class="sxs-lookup"><span data-stu-id="3104f-111">**UserUri**</span></span> <br/> |<span data-ttu-id="3104f-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3104f-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3104f-113">Универсальный код ресурса (URI) пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="3104f-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="3104f-114">**Усеруритипе**</span><span class="sxs-lookup"><span data-stu-id="3104f-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="3104f-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3104f-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3104f-116">Тип URI пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="3104f-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="3104f-117">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="3104f-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3104f-118">**Усертенант**</span><span class="sxs-lookup"><span data-stu-id="3104f-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="3104f-119">идентификатора</span><span class="sxs-lookup"><span data-stu-id="3104f-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="3104f-120">Клиент пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="3104f-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="3104f-121">Дополнительные сведения см. в [таблице "клиенты](tenants.md) ".</span><span class="sxs-lookup"><span data-stu-id="3104f-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3104f-122">**Усермессажекаунт**</span><span class="sxs-lookup"><span data-stu-id="3104f-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="3104f-123">smallint</span><span class="sxs-lookup"><span data-stu-id="3104f-123">smallint</span></span>  <br/> |<span data-ttu-id="3104f-124">Количество сообщений, отправленных пользователем во время сеанса конференции.</span><span class="sxs-lookup"><span data-stu-id="3104f-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

