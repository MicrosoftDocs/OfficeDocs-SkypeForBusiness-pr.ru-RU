---
title: Таблица Конференцемессажекаунт в Skype для бизнеса Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции для обмена мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена в этой таблице несколькими записями; одна запись для каждого пользователя.
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815377"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="81fae-104">Таблица Конференцемессажекаунт в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="81fae-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="81fae-105">Каждая запись в этой таблице представляет одного пользователя в одной конференции для обмена мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="81fae-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="81fae-106">Каждая конференция представлена в этой таблице несколькими записями; одна запись для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="81fae-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="81fae-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="81fae-107">**Column**</span></span>|<span data-ttu-id="81fae-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="81fae-108">**Data Type**</span></span>|<span data-ttu-id="81fae-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="81fae-109">**Key/Index**</span></span>|<span data-ttu-id="81fae-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="81fae-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81fae-111">**сессионидтиме**</span><span class="sxs-lookup"><span data-stu-id="81fae-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="81fae-112">datetime</span><span class="sxs-lookup"><span data-stu-id="81fae-112">datetime</span></span>  <br/> |<span data-ttu-id="81fae-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="81fae-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="81fae-114">Время экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="81fae-114">Time of conference instance.</span></span> <span data-ttu-id="81fae-115">Используется в сочетании с **сессионидсек** для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="81fae-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="81fae-116">Для получения дополнительных сведений ознакомьтесь с [таблицей "Конференции" в Skype для бизнеса Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="81fae-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="81fae-117">**сессионидсек**</span><span class="sxs-lookup"><span data-stu-id="81fae-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="81fae-118">целое</span><span class="sxs-lookup"><span data-stu-id="81fae-118">int</span></span>  <br/> |<span data-ttu-id="81fae-119">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="81fae-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="81fae-120">ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="81fae-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="81fae-121">Используется в сочетании с **сессионидтиме** для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="81fae-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="81fae-122">Для получения дополнительных сведений ознакомьтесь с [таблицей "Конференции" в Skype для бизнеса Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="81fae-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="81fae-123">**Идентификатора пользователя**</span><span class="sxs-lookup"><span data-stu-id="81fae-123">**UserId**</span></span> <br/> |<span data-ttu-id="81fae-124">целое</span><span class="sxs-lookup"><span data-stu-id="81fae-124">int</span></span>  <br/> |<span data-ttu-id="81fae-125">Другом</span><span class="sxs-lookup"><span data-stu-id="81fae-125">Foreign</span></span>  <br/> |<span data-ttu-id="81fae-126">Уникальный номер, идентифицирующий этого пользователя, на который ссылается [Таблица "Пользователи](users.md)".</span><span class="sxs-lookup"><span data-stu-id="81fae-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="81fae-127">**мессажекаунт**</span><span class="sxs-lookup"><span data-stu-id="81fae-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="81fae-128">smallint</span><span class="sxs-lookup"><span data-stu-id="81fae-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="81fae-129">Количество сообщений, отправленных этим пользователем во время данной Конференции.</span><span class="sxs-lookup"><span data-stu-id="81fae-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

