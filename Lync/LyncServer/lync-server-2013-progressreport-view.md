---
title: 'Lync Server 2013: представление Таблица progressreport'
description: 'Lync Server 2013: представление Таблица progressreport.'
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
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579795"
---
# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="24725-103">Представление Таблица progressreport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24725-103">ProgressReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24725-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="24725-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="24725-105">В представлении ProgressReport хранятся сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="24725-105">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="24725-106">Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей.</span><span class="sxs-lookup"><span data-stu-id="24725-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="24725-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24725-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24725-108">Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут относиться не к ошибкам, а к сообщениям, указывающим состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="24725-108">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24725-109">Столбец</span><span class="sxs-lookup"><span data-stu-id="24725-109">Column</span></span></th>
<th><span data-ttu-id="24725-110">Тип данных</span><span class="sxs-lookup"><span data-stu-id="24725-110">Data Type</span></span></th>
<th><span data-ttu-id="24725-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="24725-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24725-112"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="24725-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-113">datetime</span><span class="sxs-lookup"><span data-stu-id="24725-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="24725-p102">Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="24725-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24725-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="24725-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-117">int</span><span class="sxs-lookup"><span data-stu-id="24725-117">int</span></span></p></td>
<td><p><span data-ttu-id="24725-p103">Идентификационный номер ошибки. В сочетании со значением ErrorTime уникально идентифицирует ошибку.</span><span class="sxs-lookup"><span data-stu-id="24725-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24725-120"><strong>прогрессрепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="24725-120"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-121">int</span><span class="sxs-lookup"><span data-stu-id="24725-121">int</span></span></p></td>
<td><p><span data-ttu-id="24725-122">Идентификатор отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="24725-122">ID to identify the progress report.</span></span> <span data-ttu-id="24725-123">Используется для различения отчетов о ходе выполнения в рамках одного отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="24725-123">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24725-124"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="24725-124"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-125">int</span><span class="sxs-lookup"><span data-stu-id="24725-125">int</span></span></p></td>
<td><p><span data-ttu-id="24725-126">ИД диагностики для отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="24725-126">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24725-127"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="24725-127"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="24725-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="24725-129">Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</span><span class="sxs-lookup"><span data-stu-id="24725-129">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24725-130"><strong>Приложение</strong></span><span class="sxs-lookup"><span data-stu-id="24725-130"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="24725-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="24725-132">Имя приложения, в котором произошла ошибка (если отчет был отправлен компонентом сервера).</span><span class="sxs-lookup"><span data-stu-id="24725-132">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24725-133"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="24725-133"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-134">идентификатора</span><span class="sxs-lookup"><span data-stu-id="24725-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="24725-135">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="24725-135">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24725-136"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="24725-136"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-137">int</span><span class="sxs-lookup"><span data-stu-id="24725-137">int</span></span></p></td>
<td><p><span data-ttu-id="24725-138">Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="24725-138">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24725-139"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="24725-139"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="24725-140">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="24725-140">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="24725-141">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="24725-141">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

