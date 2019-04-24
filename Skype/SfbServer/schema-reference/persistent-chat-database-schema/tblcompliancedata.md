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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212616"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="f38b0-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="f38b0-103">tblComplianceData</span></span>
 
<span data-ttu-id="f38b0-104">tblComplianceData содержит события соответствия, которые не были обработаны адаптером соответствия еще.</span><span class="sxs-lookup"><span data-stu-id="f38b0-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="f38b0-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f38b0-105">**Columns**</span></span>

|<span data-ttu-id="f38b0-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f38b0-106">**Column**</span></span>|<span data-ttu-id="f38b0-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f38b0-107">**Type**</span></span>|<span data-ttu-id="f38b0-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f38b0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f38b0-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f38b0-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="f38b0-110">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f38b0-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f38b0-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="f38b0-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="f38b0-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="f38b0-112">entryDate</span></span>  <br/> |<span data-ttu-id="f38b0-113">smalldatetime, не null</span><span class="sxs-lookup"><span data-stu-id="f38b0-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="f38b0-114">Время вставки (может относиться к далекому будущему для cmplType = 9, так как запись в этом случае является всего лишь заполнителем).</span><span class="sxs-lookup"><span data-stu-id="f38b0-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="f38b0-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="f38b0-115">cmplType</span></span>  <br/> |<span data-ttu-id="f38b0-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="f38b0-116">int, not null</span></span>  <br/> | <span data-ttu-id="f38b0-117">Тип события соответствия нормативным требованиям:</span><span class="sxs-lookup"><span data-stu-id="f38b0-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="f38b0-118">1: чата</span><span class="sxs-lookup"><span data-stu-id="f38b0-118">1: Chat</span></span> <br/>  <span data-ttu-id="f38b0-119">2: ответ на чат</span><span class="sxs-lookup"><span data-stu-id="f38b0-119">2: Backchat</span></span> <br/>  <span data-ttu-id="f38b0-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="f38b0-120">3: File download</span></span> <br/>  <span data-ttu-id="f38b0-121">4: Отправка файла</span><span class="sxs-lookup"><span data-stu-id="f38b0-121">4: File upload</span></span> <br/>  <span data-ttu-id="f38b0-122">9: промежуточная передача файла</span><span class="sxs-lookup"><span data-stu-id="f38b0-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="f38b0-123">10: удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="f38b0-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="f38b0-124">11: очистка чата</span><span class="sxs-lookup"><span data-stu-id="f38b0-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="f38b0-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="f38b0-125">cmplTime</span></span>  <br/> |<span data-ttu-id="f38b0-126">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f38b0-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="f38b0-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="f38b0-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="f38b0-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="f38b0-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="f38b0-129">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="f38b0-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f38b0-130">Канал универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="f38b0-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="f38b0-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="f38b0-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="f38b0-132">bigint</span><span class="sxs-lookup"><span data-stu-id="f38b0-132">bigint</span></span>  <br/> |<span data-ttu-id="f38b0-133">Идентификатор (в соответствии с таблицей tblChat.chatId) чата.</span><span class="sxs-lookup"><span data-stu-id="f38b0-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="f38b0-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="f38b0-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="f38b0-135">int, не null</span><span class="sxs-lookup"><span data-stu-id="f38b0-135">int, not null</span></span>  <br/> |<span data-ttu-id="f38b0-136">Идентификатор субъекта плакат (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="f38b0-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="f38b0-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="f38b0-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="f38b0-138">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="f38b0-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f38b0-139">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="f38b0-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="f38b0-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="f38b0-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="f38b0-141">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="f38b0-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="f38b0-142">Сообщение (кодировка зависит от cmplType).</span><span class="sxs-lookup"><span data-stu-id="f38b0-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="f38b0-143">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="f38b0-143">**Key**</span></span>

|<span data-ttu-id="f38b0-144">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f38b0-144">**Column**</span></span>|<span data-ttu-id="f38b0-145">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f38b0-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f38b0-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f38b0-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="f38b0-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f38b0-147">Primary key.</span></span>  <br/> |
   

