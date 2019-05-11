---
title: Таблица ConferenceMessageCount в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции обмена мгновенными Сообщениями, включая число сообщений, отправленных данным пользователем. Каждой конференции представлены несколько записей в этой таблице; одна запись для каждого пользователя.
ms.openlocfilehash: f45de53333b23368351c8c5330b474cd3260192b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901431"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="85691-104">Таблица ConferenceMessageCount в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="85691-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="85691-105">Каждая запись в этой таблице представляет одного пользователя в одной конференции обмена мгновенными Сообщениями, включая число сообщений, отправленных данным пользователем.</span><span class="sxs-lookup"><span data-stu-id="85691-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="85691-106">Каждой конференции представлены несколько записей в этой таблице; одна запись для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="85691-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="85691-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="85691-107">**Column**</span></span>|<span data-ttu-id="85691-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="85691-108">**Data Type**</span></span>|<span data-ttu-id="85691-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="85691-109">**Key/Index**</span></span>|<span data-ttu-id="85691-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="85691-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85691-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="85691-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="85691-112">datetime</span><span class="sxs-lookup"><span data-stu-id="85691-112">datetime</span></span>  <br/> |<span data-ttu-id="85691-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="85691-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="85691-114">Время создания экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="85691-114">Time of conference instance.</span></span> <span data-ttu-id="85691-115">Используется совместно с **SessionIdSeq** для уникальной идентификации экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="85691-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="85691-116">В разделе [Таблица конференций в Скайп для Business Server 2015](conferences.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="85691-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="85691-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="85691-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="85691-118">целое</span><span class="sxs-lookup"><span data-stu-id="85691-118">int</span></span>  <br/> |<span data-ttu-id="85691-119">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="85691-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="85691-120">Номер идентификатора для определения экземпляра в конференции.</span><span class="sxs-lookup"><span data-stu-id="85691-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="85691-121">Используется в сочетании с **SessionIdTime** для уникальной идентификации экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="85691-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="85691-122">В разделе [Таблица конференций в Скайп для Business Server 2015](conferences.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="85691-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="85691-123">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="85691-123">**UserId**</span></span> <br/> |<span data-ttu-id="85691-124">целое</span><span class="sxs-lookup"><span data-stu-id="85691-124">int</span></span>  <br/> |<span data-ttu-id="85691-125">Внешний</span><span class="sxs-lookup"><span data-stu-id="85691-125">Foreign</span></span>  <br/> |<span data-ttu-id="85691-126">Уникальный номер, идентифицирующий этого пользователя, ссылка из [таблицы Users table](users.md).</span><span class="sxs-lookup"><span data-stu-id="85691-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="85691-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="85691-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="85691-128">smallint</span><span class="sxs-lookup"><span data-stu-id="85691-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="85691-129">Число сообщений, отправленных данным пользователем в течение этой конференции.</span><span class="sxs-lookup"><span data-stu-id="85691-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

