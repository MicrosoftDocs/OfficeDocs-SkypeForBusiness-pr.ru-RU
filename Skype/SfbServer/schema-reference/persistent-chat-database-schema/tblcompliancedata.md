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
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295512"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="fd7a7-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="fd7a7-103">tblComplianceData</span></span>
 
<span data-ttu-id="fd7a7-104">Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fd7a7-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="fd7a7-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="fd7a7-105">**Columns**</span></span>

|<span data-ttu-id="fd7a7-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fd7a7-106">**Column**</span></span>|<span data-ttu-id="fd7a7-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fd7a7-107">**Type**</span></span>|<span data-ttu-id="fd7a7-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fd7a7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd7a7-109">Кмплевентид</span><span class="sxs-lookup"><span data-stu-id="fd7a7-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="fd7a7-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd7a7-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="fd7a7-111">Код события.</span><span class="sxs-lookup"><span data-stu-id="fd7a7-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="fd7a7-112">Ентридате</span><span class="sxs-lookup"><span data-stu-id="fd7a7-112">entryDate</span></span>  <br/> |<span data-ttu-id="fd7a7-113">smalldatetime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd7a7-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="fd7a7-114">Время вставки (может быть в будущем для Кмплтипе = 9, так как в этом случае запись является заполнителем в этом случае).</span><span class="sxs-lookup"><span data-stu-id="fd7a7-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="fd7a7-115">Кмплтипе</span><span class="sxs-lookup"><span data-stu-id="fd7a7-115">cmplType</span></span>  <br/> |<span data-ttu-id="fd7a7-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd7a7-116">int, not null</span></span>  <br/> | <span data-ttu-id="fd7a7-117">Тип события соответствия:</span><span class="sxs-lookup"><span data-stu-id="fd7a7-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="fd7a7-118">1: чат</span><span class="sxs-lookup"><span data-stu-id="fd7a7-118">1: Chat</span></span> <br/>  <span data-ttu-id="fd7a7-119">2: чат</span><span class="sxs-lookup"><span data-stu-id="fd7a7-119">2: Backchat</span></span> <br/>  <span data-ttu-id="fd7a7-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="fd7a7-120">3: File download</span></span> <br/>  <span data-ttu-id="fd7a7-121">4: Отправка файлов</span><span class="sxs-lookup"><span data-stu-id="fd7a7-121">4: File upload</span></span> <br/>  <span data-ttu-id="fd7a7-122">9: подготовка к передаче файлов</span><span class="sxs-lookup"><span data-stu-id="fd7a7-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="fd7a7-123">10: удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="fd7a7-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="fd7a7-124">11: Очистка чата</span><span class="sxs-lookup"><span data-stu-id="fd7a7-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="fd7a7-125">Кмплтиме</span><span class="sxs-lookup"><span data-stu-id="fd7a7-125">cmplTime</span></span>  <br/> |<span data-ttu-id="fd7a7-126">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd7a7-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="fd7a7-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="fd7a7-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="fd7a7-128">Кмплчаннелури</span><span class="sxs-lookup"><span data-stu-id="fd7a7-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="fd7a7-129">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd7a7-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="fd7a7-130">Универсальный код ресурса (URI) канала.</span><span class="sxs-lookup"><span data-stu-id="fd7a7-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="fd7a7-131">Кмплчатид</span><span class="sxs-lookup"><span data-stu-id="fd7a7-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="fd7a7-132">bigint</span><span class="sxs-lookup"><span data-stu-id="fd7a7-132">bigint</span></span>  <br/> |<span data-ttu-id="fd7a7-133">ИДЕНТИФИКАТОР чата (соответствующая таблице Тблчат. Чатид).</span><span class="sxs-lookup"><span data-stu-id="fd7a7-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="fd7a7-134">Кмплусерид</span><span class="sxs-lookup"><span data-stu-id="fd7a7-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="fd7a7-135">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd7a7-135">int, not null</span></span>  <br/> |<span data-ttu-id="fd7a7-136">Идентификатор участника афиши (соответствующий таблице ТблпринЦипал. Принид).</span><span class="sxs-lookup"><span data-stu-id="fd7a7-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="fd7a7-137">Кмплусерури</span><span class="sxs-lookup"><span data-stu-id="fd7a7-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="fd7a7-138">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd7a7-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="fd7a7-139">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="fd7a7-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="fd7a7-140">Кмплмессаже</span><span class="sxs-lookup"><span data-stu-id="fd7a7-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="fd7a7-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="fd7a7-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="fd7a7-142">Сообщение (Кодировка зависит от Кмплтипе).</span><span class="sxs-lookup"><span data-stu-id="fd7a7-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="fd7a7-143">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="fd7a7-143">**Key**</span></span>

|<span data-ttu-id="fd7a7-144">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fd7a7-144">**Column**</span></span>|<span data-ttu-id="fd7a7-145">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fd7a7-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fd7a7-146">Кмплевентид</span><span class="sxs-lookup"><span data-stu-id="fd7a7-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="fd7a7-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="fd7a7-147">Primary key.</span></span>  <br/> |
   

