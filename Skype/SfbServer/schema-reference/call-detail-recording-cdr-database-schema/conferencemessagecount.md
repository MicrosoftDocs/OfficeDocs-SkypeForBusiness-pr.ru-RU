---
title: Таблица ConferenceMessageCount в Skype для бизнеса Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции с мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; одна запись для каждого пользователя.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813279"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4a48b-104">Таблица ConferenceMessageCount в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="4a48b-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4a48b-105">Каждая запись в этой таблице представляет одного пользователя в одной конференции с мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="4a48b-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="4a48b-106">Каждая конференция представлена несколькими записями в этой таблице; одна запись для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a48b-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="4a48b-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4a48b-107">**Column**</span></span>|<span data-ttu-id="4a48b-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4a48b-108">**Data Type**</span></span>|<span data-ttu-id="4a48b-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4a48b-109">**Key/Index**</span></span>|<span data-ttu-id="4a48b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="4a48b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a48b-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="4a48b-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="4a48b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4a48b-112">datetime</span></span>  <br/> |<span data-ttu-id="4a48b-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="4a48b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4a48b-114">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="4a48b-114">Time of conference instance.</span></span> <span data-ttu-id="4a48b-115">Используется в сочетании с **SessionIdSeq** для уникальной идентификации экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="4a48b-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="4a48b-116">Дополнительные сведения см. в таблице ["Конференции" в Skype для бизнеса Server 2015.](conferences.md)</span><span class="sxs-lookup"><span data-stu-id="4a48b-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4a48b-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="4a48b-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="4a48b-118">int</span><span class="sxs-lookup"><span data-stu-id="4a48b-118">int</span></span>  <br/> |<span data-ttu-id="4a48b-119">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="4a48b-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4a48b-120">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="4a48b-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="4a48b-121">Используется в сочетании с **SessionIdTime** для уникальной идентификации экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="4a48b-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="4a48b-122">Дополнительные сведения см. в таблице ["Конференции" в Skype для бизнеса Server 2015.](conferences.md)</span><span class="sxs-lookup"><span data-stu-id="4a48b-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4a48b-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="4a48b-123">**UserId**</span></span> <br/> |<span data-ttu-id="4a48b-124">int</span><span class="sxs-lookup"><span data-stu-id="4a48b-124">int</span></span>  <br/> |<span data-ttu-id="4a48b-125">Внешняя</span><span class="sxs-lookup"><span data-stu-id="4a48b-125">Foreign</span></span>  <br/> |<span data-ttu-id="4a48b-126">Уникальный номер, идентифицирующий этого пользователя, на который ссылается [таблица Users.](users.md)</span><span class="sxs-lookup"><span data-stu-id="4a48b-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="4a48b-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="4a48b-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="4a48b-128">smallint</span><span class="sxs-lookup"><span data-stu-id="4a48b-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="4a48b-129">Количество сообщений, отправленных этим пользователем во время этой конференции.</span><span class="sxs-lookup"><span data-stu-id="4a48b-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

