---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814667"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="e41df-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="e41df-103">tblComplianceData</span></span>
 
<span data-ttu-id="e41df-104">Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e41df-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="e41df-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="e41df-105">**Columns**</span></span>

|<span data-ttu-id="e41df-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e41df-106">**Column**</span></span>|<span data-ttu-id="e41df-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e41df-107">**Type**</span></span>|<span data-ttu-id="e41df-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e41df-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e41df-109">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="e41df-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="e41df-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e41df-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="e41df-111">Код события.</span><span class="sxs-lookup"><span data-stu-id="e41df-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="e41df-112">ентридате</span><span class="sxs-lookup"><span data-stu-id="e41df-112">entryDate</span></span>  <br/> |<span data-ttu-id="e41df-113">smalldatetime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e41df-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="e41df-114">Время вставки (может быть в будущем для Кмплтипе = 9, так как в этом случае запись является заполнителем в этом случае).</span><span class="sxs-lookup"><span data-stu-id="e41df-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="e41df-115">кмплтипе</span><span class="sxs-lookup"><span data-stu-id="e41df-115">cmplType</span></span>  <br/> |<span data-ttu-id="e41df-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e41df-116">int, not null</span></span>  <br/> | <span data-ttu-id="e41df-117">Тип события соответствия:</span><span class="sxs-lookup"><span data-stu-id="e41df-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="e41df-118">1: чат</span><span class="sxs-lookup"><span data-stu-id="e41df-118">1: Chat</span></span> <br/>  <span data-ttu-id="e41df-119">2: чат</span><span class="sxs-lookup"><span data-stu-id="e41df-119">2: Backchat</span></span> <br/>  <span data-ttu-id="e41df-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="e41df-120">3: File download</span></span> <br/>  <span data-ttu-id="e41df-121">4: Отправка файлов</span><span class="sxs-lookup"><span data-stu-id="e41df-121">4: File upload</span></span> <br/>  <span data-ttu-id="e41df-122">9: подготовка к передаче файлов</span><span class="sxs-lookup"><span data-stu-id="e41df-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="e41df-123">10: удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="e41df-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="e41df-124">11: Очистка чата</span><span class="sxs-lookup"><span data-stu-id="e41df-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="e41df-125">кмплтиме</span><span class="sxs-lookup"><span data-stu-id="e41df-125">cmplTime</span></span>  <br/> |<span data-ttu-id="e41df-126">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e41df-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="e41df-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="e41df-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="e41df-128">кмплчаннелури</span><span class="sxs-lookup"><span data-stu-id="e41df-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="e41df-129">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e41df-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e41df-130">Универсальный код ресурса (URI) канала.</span><span class="sxs-lookup"><span data-stu-id="e41df-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="e41df-131">кмплчатид</span><span class="sxs-lookup"><span data-stu-id="e41df-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="e41df-132">bigint</span><span class="sxs-lookup"><span data-stu-id="e41df-132">bigint</span></span>  <br/> |<span data-ttu-id="e41df-133">ИДЕНТИФИКАТОР чата (соответствующая таблице Тблчат. Чатид).</span><span class="sxs-lookup"><span data-stu-id="e41df-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="e41df-134">кмплусерид</span><span class="sxs-lookup"><span data-stu-id="e41df-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="e41df-135">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e41df-135">int, not null</span></span>  <br/> |<span data-ttu-id="e41df-136">Идентификатор участника афиши (соответствующий таблице ТблпринЦипал. Принид).</span><span class="sxs-lookup"><span data-stu-id="e41df-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="e41df-137">кмплусерури</span><span class="sxs-lookup"><span data-stu-id="e41df-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="e41df-138">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e41df-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e41df-139">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="e41df-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="e41df-140">кмплмессаже</span><span class="sxs-lookup"><span data-stu-id="e41df-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="e41df-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="e41df-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="e41df-142">Сообщение (Кодировка зависит от Кмплтипе).</span><span class="sxs-lookup"><span data-stu-id="e41df-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="e41df-143">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="e41df-143">**Key**</span></span>

|<span data-ttu-id="e41df-144">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e41df-144">**Column**</span></span>|<span data-ttu-id="e41df-145">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e41df-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e41df-146">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="e41df-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="e41df-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e41df-147">Primary key.</span></span>  <br/> |
   

