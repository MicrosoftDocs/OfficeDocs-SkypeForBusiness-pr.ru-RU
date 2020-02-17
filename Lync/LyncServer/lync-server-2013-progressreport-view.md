---
title: 'Lync Server 2013: представление Таблица progressreport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="3590d-102">Представление Таблица progressreport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3590d-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3590d-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3590d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3590d-104">В представлении ProgressReport хранятся сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="3590d-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="3590d-105">Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей.</span><span class="sxs-lookup"><span data-stu-id="3590d-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="3590d-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3590d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3590d-107">Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут относиться не к ошибкам, а к сообщениям, указывающим состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="3590d-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3590d-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="3590d-108">Column</span></span></th>
<th><span data-ttu-id="3590d-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3590d-109">Data Type</span></span></th>
<th><span data-ttu-id="3590d-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="3590d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3590d-111"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3590d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="3590d-p102">Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="3590d-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3590d-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-116">int</span><span class="sxs-lookup"><span data-stu-id="3590d-116">int</span></span></p></td>
<td><p><span data-ttu-id="3590d-p103">Идентификационный номер ошибки. В сочетании со значением ErrorTime уникально идентифицирует ошибку.</span><span class="sxs-lookup"><span data-stu-id="3590d-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3590d-119"><strong>прогрессрепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-120">int</span><span class="sxs-lookup"><span data-stu-id="3590d-120">int</span></span></p></td>
<td><p><span data-ttu-id="3590d-121">Идентификатор отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="3590d-121">ID to identify the progress report.</span></span> <span data-ttu-id="3590d-122">Используется для различения отчетов о ходе выполнения в рамках одного отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="3590d-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3590d-123"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-124">int</span><span class="sxs-lookup"><span data-stu-id="3590d-124">int</span></span></p></td>
<td><p><span data-ttu-id="3590d-125">ИД диагностики для отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="3590d-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3590d-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3590d-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3590d-128">Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</span><span class="sxs-lookup"><span data-stu-id="3590d-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3590d-129"><strong>Приложение</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3590d-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3590d-131">Имя приложения, в котором произошла ошибка (если отчет был отправлен компонентом сервера).</span><span class="sxs-lookup"><span data-stu-id="3590d-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3590d-132"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-133">идентификатора</span><span class="sxs-lookup"><span data-stu-id="3590d-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3590d-134">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="3590d-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3590d-135"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-136">int</span><span class="sxs-lookup"><span data-stu-id="3590d-136">int</span></span></p></td>
<td><p><span data-ttu-id="3590d-137">Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="3590d-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3590d-138"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="3590d-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="3590d-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="3590d-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="3590d-140">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="3590d-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

