---
title: Представление Прогрессрепорт
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: В представлении Прогрессрепорт хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения будут записываться только для звонков и сеансов, которые определяет Lync Server 2013, может быть полезен в целях диагностики. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814987"
---
# <a name="progressreport-view"></a><span data-ttu-id="61f7d-105">Представление Прогрессрепорт</span><span class="sxs-lookup"><span data-stu-id="61f7d-105">ProgressReport view</span></span>
 
<span data-ttu-id="61f7d-106">В представлении Прогрессрепорт хранятся сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="61f7d-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="61f7d-107">Отчеты о ходе выполнения будут записываться только для звонков и сеансов, которые определяет Lync Server 2013, может быть полезен в целях диагностики.</span><span class="sxs-lookup"><span data-stu-id="61f7d-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="61f7d-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61f7d-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61f7d-109">Поля Еррортиме, Ерроррепортсек и Прогрессрепортсек не обязательно ссылаются на ошибки, а также на сообщения, указывающие на состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="61f7d-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="61f7d-110">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="61f7d-110">**Column**</span></span>|<span data-ttu-id="61f7d-111">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="61f7d-111">**Data Type**</span></span>|<span data-ttu-id="61f7d-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="61f7d-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61f7d-113">**еррортиме**</span><span class="sxs-lookup"><span data-stu-id="61f7d-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="61f7d-114">datetime</span><span class="sxs-lookup"><span data-stu-id="61f7d-114">datetime</span></span>  <br/> |<span data-ttu-id="61f7d-115">Время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="61f7d-115">Time of error occurred.</span></span> <span data-ttu-id="61f7d-116">Используется в сочетании с Ерроррепортсек для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="61f7d-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="61f7d-117">**ерроррепортсек**</span><span class="sxs-lookup"><span data-stu-id="61f7d-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="61f7d-118">целое</span><span class="sxs-lookup"><span data-stu-id="61f7d-118">int</span></span>  <br/> |<span data-ttu-id="61f7d-119">ИДЕНТИФИКАЦИОНный номер для идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="61f7d-119">ID number to identify the error.</span></span> <span data-ttu-id="61f7d-120">Используется в сочетании с Еррортиме для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="61f7d-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="61f7d-121">**прогрессрепортсек**</span><span class="sxs-lookup"><span data-stu-id="61f7d-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="61f7d-122">целое</span><span class="sxs-lookup"><span data-stu-id="61f7d-122">int</span></span>  <br/> |<span data-ttu-id="61f7d-123">Идентификатор для идентификации отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="61f7d-123">ID to identify the progress report.</span></span> <span data-ttu-id="61f7d-124">Используется, чтобы отличать отчеты о ходе выполнения одного отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="61f7d-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="61f7d-125">**мсдиагид**</span><span class="sxs-lookup"><span data-stu-id="61f7d-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="61f7d-126">целое</span><span class="sxs-lookup"><span data-stu-id="61f7d-126">int</span></span>  <br/> |<span data-ttu-id="61f7d-127">Идентификатор диагностики для отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="61f7d-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="61f7d-128">**Источник**</span><span class="sxs-lookup"><span data-stu-id="61f7d-128">**Source**</span></span> <br/> |<span data-ttu-id="61f7d-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="61f7d-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="61f7d-130">Имя сервера, отправившего ошибку (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="61f7d-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="61f7d-131">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="61f7d-131">**Application**</span></span> <br/> |<span data-ttu-id="61f7d-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="61f7d-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="61f7d-133">Имя приложения, которое поступило об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="61f7d-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="61f7d-134">**телеметрид**</span><span class="sxs-lookup"><span data-stu-id="61f7d-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="61f7d-135">идентификатора</span><span class="sxs-lookup"><span data-stu-id="61f7d-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="61f7d-136">Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</span><span class="sxs-lookup"><span data-stu-id="61f7d-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="61f7d-137">**сессионсетуптиме**</span><span class="sxs-lookup"><span data-stu-id="61f7d-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="61f7d-138">целое</span><span class="sxs-lookup"><span data-stu-id="61f7d-138">int</span></span>  <br/> |<span data-ttu-id="61f7d-139">Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="61f7d-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="61f7d-140">**мсдиагхеадер**</span><span class="sxs-lookup"><span data-stu-id="61f7d-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="61f7d-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="61f7d-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="61f7d-142">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="61f7d-142">Additional error information.</span></span>  <br/> |
   

