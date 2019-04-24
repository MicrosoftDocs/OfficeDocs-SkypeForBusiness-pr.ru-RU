---
title: Таблица ConferenceMessageCount в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции обмена мгновенными Сообщениями, включая число сообщений, отправленных данным пользователем. Каждой конференции представлены несколько записей в этой таблице; одна запись для каждого пользователя.
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213279"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f806e-104">Таблица ConferenceMessageCount в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f806e-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f806e-105">Каждая запись в этой таблице представляет одного пользователя в одной конференции обмена мгновенными Сообщениями, включая число сообщений, отправленных данным пользователем.</span><span class="sxs-lookup"><span data-stu-id="f806e-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="f806e-106">Каждой конференции представлены несколько записей в этой таблице; одна запись для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f806e-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="f806e-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f806e-107">**Column**</span></span>|<span data-ttu-id="f806e-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="f806e-108">**Data Type**</span></span>|<span data-ttu-id="f806e-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="f806e-109">**Key/Index**</span></span>|<span data-ttu-id="f806e-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="f806e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f806e-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="f806e-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="f806e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f806e-112">datetime</span></span>  <br/> |<span data-ttu-id="f806e-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="f806e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f806e-114">Время создания экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="f806e-114">Time of conference instance.</span></span> <span data-ttu-id="f806e-115">Используется совместно с **SessionIdSeq** для уникальной идентификации экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="f806e-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="f806e-116">В разделе [Таблица конференций в Скайп для Business Server 2015](conferences.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="f806e-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f806e-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="f806e-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="f806e-118">целое</span><span class="sxs-lookup"><span data-stu-id="f806e-118">int</span></span>  <br/> |<span data-ttu-id="f806e-119">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="f806e-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f806e-120">Номер идентификатора для определения экземпляра в конференции.</span><span class="sxs-lookup"><span data-stu-id="f806e-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="f806e-121">Используется в сочетании с **SessionIdTime** для уникальной идентификации экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="f806e-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="f806e-122">В разделе [Таблица конференций в Скайп для Business Server 2015](conferences.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="f806e-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f806e-123">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="f806e-123">**UserId**</span></span> <br/> |<span data-ttu-id="f806e-124">целое</span><span class="sxs-lookup"><span data-stu-id="f806e-124">int</span></span>  <br/> |<span data-ttu-id="f806e-125">Внешний</span><span class="sxs-lookup"><span data-stu-id="f806e-125">Foreign</span></span>  <br/> |<span data-ttu-id="f806e-126">Уникальный номер, идентифицирующий этого пользователя, ссылка из [таблицы Users table](users.md).</span><span class="sxs-lookup"><span data-stu-id="f806e-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="f806e-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="f806e-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="f806e-128">smallint</span><span class="sxs-lookup"><span data-stu-id="f806e-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="f806e-129">Число сообщений, отправленных данным пользователем в течение этой конференции.</span><span class="sxs-lookup"><span data-stu-id="f806e-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

