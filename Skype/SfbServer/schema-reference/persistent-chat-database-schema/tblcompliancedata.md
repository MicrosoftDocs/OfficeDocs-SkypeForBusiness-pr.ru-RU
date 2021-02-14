---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809859"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="5d561-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="5d561-103">tblComplianceData</span></span>
 
<span data-ttu-id="5d561-104">tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.</span><span class="sxs-lookup"><span data-stu-id="5d561-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="5d561-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="5d561-105">**Columns**</span></span>

|<span data-ttu-id="5d561-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5d561-106">**Column**</span></span>|<span data-ttu-id="5d561-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5d561-107">**Type**</span></span>|<span data-ttu-id="5d561-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5d561-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d561-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5d561-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="5d561-110">bigint, не NULL</span><span class="sxs-lookup"><span data-stu-id="5d561-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="5d561-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="5d561-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="5d561-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="5d561-112">entryDate</span></span>  <br/> |<span data-ttu-id="5d561-113">smalldatetime, не NULL</span><span class="sxs-lookup"><span data-stu-id="5d561-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="5d561-114">Время вставки (может относиться к далекому будущему для  cmplType=9, так как в этом случае запись является всего лишь заполнителем).</span><span class="sxs-lookup"><span data-stu-id="5d561-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="5d561-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="5d561-115">cmplType</span></span>  <br/> |<span data-ttu-id="5d561-116">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="5d561-116">int, not null</span></span>  <br/> | <span data-ttu-id="5d561-117">Типа события соответствия нормативным требованиям:</span><span class="sxs-lookup"><span data-stu-id="5d561-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="5d561-118">1: Чат</span><span class="sxs-lookup"><span data-stu-id="5d561-118">1: Chat</span></span> <br/>  <span data-ttu-id="5d561-119">2: Ответ на чат</span><span class="sxs-lookup"><span data-stu-id="5d561-119">2: Backchat</span></span> <br/>  <span data-ttu-id="5d561-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="5d561-120">3: File download</span></span> <br/>  <span data-ttu-id="5d561-121">4: Отправка файла</span><span class="sxs-lookup"><span data-stu-id="5d561-121">4: File upload</span></span> <br/>  <span data-ttu-id="5d561-122">9: Промежуточная передача файла</span><span class="sxs-lookup"><span data-stu-id="5d561-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="5d561-123">10: Удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="5d561-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="5d561-124">11: Очистка чата</span><span class="sxs-lookup"><span data-stu-id="5d561-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="5d561-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="5d561-125">cmplTime</span></span>  <br/> |<span data-ttu-id="5d561-126">bigint, не NULL</span><span class="sxs-lookup"><span data-stu-id="5d561-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="5d561-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="5d561-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="5d561-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="5d561-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="5d561-129">nvarchar (255), не NULL</span><span class="sxs-lookup"><span data-stu-id="5d561-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5d561-130">Универсальный код ресурса (URI) для канала.</span><span class="sxs-lookup"><span data-stu-id="5d561-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="5d561-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="5d561-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="5d561-132">bigint</span><span class="sxs-lookup"><span data-stu-id="5d561-132">bigint</span></span>  <br/> |<span data-ttu-id="5d561-133">Идентификатор чата (в соответствии с таблицей tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="5d561-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="5d561-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="5d561-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="5d561-135">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="5d561-135">int, not null</span></span>  <br/> |<span data-ttu-id="5d561-136">Идентификатор субъекта для отправителя (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="5d561-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="5d561-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="5d561-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="5d561-138">nvarchar (255), не NULL</span><span class="sxs-lookup"><span data-stu-id="5d561-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5d561-139">Универсальный код ресурса (URI) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d561-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="5d561-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="5d561-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="5d561-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5d561-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="5d561-142">Сообщение (кодировка зависит от cmplType).</span><span class="sxs-lookup"><span data-stu-id="5d561-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="5d561-143">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="5d561-143">**Key**</span></span>

|<span data-ttu-id="5d561-144">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5d561-144">**Column**</span></span>|<span data-ttu-id="5d561-145">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5d561-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d561-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5d561-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="5d561-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5d561-147">Primary key.</span></span>  <br/> |
   

