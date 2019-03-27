---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData содержит события соответствия, которые не были обработаны адаптером соответствия еще.
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885823"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="91864-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="91864-103">tblComplianceData</span></span>
 
<span data-ttu-id="91864-104">tblComplianceData содержит события соответствия, которые не были обработаны адаптером соответствия еще.</span><span class="sxs-lookup"><span data-stu-id="91864-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="91864-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="91864-105">**Columns**</span></span>

|<span data-ttu-id="91864-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="91864-106">**Column**</span></span>|<span data-ttu-id="91864-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="91864-107">**Type**</span></span>|<span data-ttu-id="91864-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="91864-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="91864-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="91864-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="91864-110">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="91864-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="91864-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="91864-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="91864-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="91864-112">entryDate</span></span>  <br/> |<span data-ttu-id="91864-113">smalldatetime, не null</span><span class="sxs-lookup"><span data-stu-id="91864-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="91864-114">Время вставки (может относиться к далекому будущему для cmplType = 9, так как запись в этом случае является всего лишь заполнителем).</span><span class="sxs-lookup"><span data-stu-id="91864-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="91864-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="91864-115">cmplType</span></span>  <br/> |<span data-ttu-id="91864-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="91864-116">int, not null</span></span>  <br/> | <span data-ttu-id="91864-117">Тип события соответствия нормативным требованиям:</span><span class="sxs-lookup"><span data-stu-id="91864-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="91864-118">1: чата</span><span class="sxs-lookup"><span data-stu-id="91864-118">1: Chat</span></span> <br/>  <span data-ttu-id="91864-119">2: ответ на чат</span><span class="sxs-lookup"><span data-stu-id="91864-119">2: Backchat</span></span> <br/>  <span data-ttu-id="91864-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="91864-120">3: File download</span></span> <br/>  <span data-ttu-id="91864-121">4: Отправка файла</span><span class="sxs-lookup"><span data-stu-id="91864-121">4: File upload</span></span> <br/>  <span data-ttu-id="91864-122">9: промежуточная передача файла</span><span class="sxs-lookup"><span data-stu-id="91864-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="91864-123">10: удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="91864-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="91864-124">11: очистка чата</span><span class="sxs-lookup"><span data-stu-id="91864-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="91864-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="91864-125">cmplTime</span></span>  <br/> |<span data-ttu-id="91864-126">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="91864-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="91864-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="91864-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="91864-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="91864-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="91864-129">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="91864-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="91864-130">Канал универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="91864-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="91864-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="91864-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="91864-132">bigint</span><span class="sxs-lookup"><span data-stu-id="91864-132">bigint</span></span>  <br/> |<span data-ttu-id="91864-133">Идентификатор (в соответствии с таблицей tblChat.chatId) чата.</span><span class="sxs-lookup"><span data-stu-id="91864-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="91864-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="91864-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="91864-135">int, не null</span><span class="sxs-lookup"><span data-stu-id="91864-135">int, not null</span></span>  <br/> |<span data-ttu-id="91864-136">Идентификатор субъекта плакат (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="91864-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="91864-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="91864-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="91864-138">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="91864-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="91864-139">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="91864-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="91864-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="91864-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="91864-141">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="91864-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="91864-142">Сообщение (кодировка зависит от cmplType).</span><span class="sxs-lookup"><span data-stu-id="91864-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="91864-143">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="91864-143">**Key**</span></span>

|<span data-ttu-id="91864-144">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="91864-144">**Column**</span></span>|<span data-ttu-id="91864-145">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="91864-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="91864-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="91864-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="91864-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="91864-147">Primary key.</span></span>  <br/> |
   

