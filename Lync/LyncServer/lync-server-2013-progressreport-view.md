---
title: 'Lync Server 2013: представление Прогрессрепорт'
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
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="c70a1-102">Прогрессрепорт представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c70a1-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c70a1-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c70a1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c70a1-104">В представлении Прогрессрепорт хранятся сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="c70a1-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="c70a1-105">Отчеты о ходе выполнения будут записываться только для звонков и сеансов, которые определяет Lync Server 2013, может быть полезен в целях диагностики.</span><span class="sxs-lookup"><span data-stu-id="c70a1-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="c70a1-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c70a1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c70a1-107">Поля Еррортиме, Ерроррепортсек и Прогрессрепортсек не обязательно ссылаются на ошибки, а также на сообщения, указывающие на состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="c70a1-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c70a1-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="c70a1-108">Column</span></span></th>
<th><span data-ttu-id="c70a1-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c70a1-109">Data Type</span></span></th>
<th><span data-ttu-id="c70a1-110">Подробности</span><span class="sxs-lookup"><span data-stu-id="c70a1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c70a1-111"><strong>еррортиме</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c70a1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c70a1-113">Время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="c70a1-113">Time of error occurred.</span></span> <span data-ttu-id="c70a1-114">Используется в сочетании с Ерроррепортсек для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="c70a1-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70a1-115"><strong>ерроррепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-116">целое</span><span class="sxs-lookup"><span data-stu-id="c70a1-116">int</span></span></p></td>
<td><p><span data-ttu-id="c70a1-117">ИДЕНТИФИКАЦИОНный номер для идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="c70a1-117">ID number to identify the error.</span></span> <span data-ttu-id="c70a1-118">Используется в сочетании с Еррортиме для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="c70a1-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c70a1-119"><strong>прогрессрепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-120">целое</span><span class="sxs-lookup"><span data-stu-id="c70a1-120">int</span></span></p></td>
<td><p><span data-ttu-id="c70a1-121">Идентификатор для идентификации отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="c70a1-121">ID to identify the progress report.</span></span> <span data-ttu-id="c70a1-122">Используется, чтобы отличать отчеты о ходе выполнения одного отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c70a1-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70a1-123"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-124">целое</span><span class="sxs-lookup"><span data-stu-id="c70a1-124">int</span></span></p></td>
<td><p><span data-ttu-id="c70a1-125">Идентификатор диагностики для отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c70a1-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c70a1-126"><strong>Источник</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c70a1-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c70a1-128">Имя сервера, отправившего ошибку (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="c70a1-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70a1-129"><strong>Приложение</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c70a1-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c70a1-131">Имя приложения, которое поступило об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="c70a1-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c70a1-132"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-133">идентификатора</span><span class="sxs-lookup"><span data-stu-id="c70a1-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c70a1-134">Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</span><span class="sxs-lookup"><span data-stu-id="c70a1-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70a1-135"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-136">целое</span><span class="sxs-lookup"><span data-stu-id="c70a1-136">int</span></span></p></td>
<td><p><span data-ttu-id="c70a1-137">Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="c70a1-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c70a1-138"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="c70a1-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="c70a1-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="c70a1-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="c70a1-140">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c70a1-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

