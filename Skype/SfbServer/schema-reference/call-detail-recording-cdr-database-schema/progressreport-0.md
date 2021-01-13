---
title: Представление ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: В представлении ProgressReport хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823189"
---
# <a name="progressreport-view"></a><span data-ttu-id="4454c-105">Представление ProgressReport</span><span class="sxs-lookup"><span data-stu-id="4454c-105">ProgressReport view</span></span>
 
<span data-ttu-id="4454c-106">В представлении ProgressReport хранятся сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="4454c-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="4454c-107">Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей.</span><span class="sxs-lookup"><span data-stu-id="4454c-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="4454c-108">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4454c-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4454c-109">Поля ErrorTime, ErrorReportSeq и ProgressReportSeq ссылаются не на ошибки, а на сообщения, которые указывают состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="4454c-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="4454c-110">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4454c-110">**Column**</span></span>|<span data-ttu-id="4454c-111">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4454c-111">**Data Type**</span></span>|<span data-ttu-id="4454c-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="4454c-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4454c-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="4454c-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="4454c-114">datetime</span><span class="sxs-lookup"><span data-stu-id="4454c-114">datetime</span></span>  <br/> |<span data-ttu-id="4454c-p103">Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="4454c-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="4454c-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="4454c-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="4454c-118">int</span><span class="sxs-lookup"><span data-stu-id="4454c-118">int</span></span>  <br/> |<span data-ttu-id="4454c-p104">Идентификационный номер ошибки. В сочетании со значением ErrorTime уникально идентифицирует ошибку.</span><span class="sxs-lookup"><span data-stu-id="4454c-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="4454c-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="4454c-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="4454c-122">int</span><span class="sxs-lookup"><span data-stu-id="4454c-122">int</span></span>  <br/> |<span data-ttu-id="4454c-123">Идентификатор отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="4454c-123">ID to identify the progress report.</span></span> <span data-ttu-id="4454c-124">Используется для различения отчетов о ходе выполнения в рамках одного отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="4454c-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="4454c-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="4454c-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="4454c-126">int</span><span class="sxs-lookup"><span data-stu-id="4454c-126">int</span></span>  <br/> |<span data-ttu-id="4454c-127">ИД диагностики для отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="4454c-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="4454c-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="4454c-128">**Source**</span></span> <br/> |<span data-ttu-id="4454c-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4454c-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4454c-130">Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</span><span class="sxs-lookup"><span data-stu-id="4454c-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="4454c-131">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="4454c-131">**Application**</span></span> <br/> |<span data-ttu-id="4454c-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4454c-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4454c-133">Имя приложения, в котором произошла ошибка (если отчет был отправлен компонентом сервера).</span><span class="sxs-lookup"><span data-stu-id="4454c-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="4454c-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="4454c-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="4454c-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4454c-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4454c-136">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="4454c-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="4454c-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="4454c-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="4454c-138">int</span><span class="sxs-lookup"><span data-stu-id="4454c-138">int</span></span>  <br/> |<span data-ttu-id="4454c-139">Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="4454c-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="4454c-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="4454c-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="4454c-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="4454c-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="4454c-142">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4454c-142">Additional error information.</span></span>  <br/> |
   

