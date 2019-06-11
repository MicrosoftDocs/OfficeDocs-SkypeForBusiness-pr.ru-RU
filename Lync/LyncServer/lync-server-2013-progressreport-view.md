---
title: 'Lync Server 2013: представление Прогрессрепорт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423d99211a89ef328bc62aca89a9b65141e128ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="98e59-102">Прогрессрепорт представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e59-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98e59-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="98e59-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="98e59-104">В представлении Прогрессрепорт хранятся сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="98e59-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="98e59-105">Отчеты о ходе выполнения будут записываться только для звонков и сеансов, которые определяет Lync Server 2013, может быть полезен в целях диагностики.</span><span class="sxs-lookup"><span data-stu-id="98e59-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="98e59-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98e59-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98e59-107">Поля Еррортиме, Ерроррепортсек и Прогрессрепортсек не обязательно ссылаются на ошибки, а также на сообщения, указывающие на состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="98e59-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98e59-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="98e59-108">Column</span></span></th>
<th><span data-ttu-id="98e59-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="98e59-109">Data Type</span></span></th>
<th><span data-ttu-id="98e59-110">Подробности</span><span class="sxs-lookup"><span data-stu-id="98e59-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98e59-111"><strong>Еррортиме</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-112">datetime</span><span class="sxs-lookup"><span data-stu-id="98e59-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="98e59-113">Время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="98e59-113">Time of error occurred.</span></span> <span data-ttu-id="98e59-114">Используется в сочетании с Ерроррепортсек для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="98e59-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e59-115"><strong>Ерроррепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-116">целое</span><span class="sxs-lookup"><span data-stu-id="98e59-116">int</span></span></p></td>
<td><p><span data-ttu-id="98e59-117">ИДЕНТИФИКАЦИОНный номер для идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="98e59-117">ID number to identify the error.</span></span> <span data-ttu-id="98e59-118">Используется в сочетании с Еррортиме для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="98e59-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e59-119"><strong>Прогрессрепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-120">целое</span><span class="sxs-lookup"><span data-stu-id="98e59-120">int</span></span></p></td>
<td><p><span data-ttu-id="98e59-121">Идентификатор для идентификации отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="98e59-121">ID to identify the progress report.</span></span> <span data-ttu-id="98e59-122">Используется, чтобы отличать отчеты о ходе выполнения одного отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="98e59-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e59-123"><strong>Мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-124">целое</span><span class="sxs-lookup"><span data-stu-id="98e59-124">int</span></span></p></td>
<td><p><span data-ttu-id="98e59-125">Идентификатор диагностики для отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="98e59-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e59-126"><strong>Источник</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="98e59-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="98e59-128">Имя сервера, отправившего ошибку (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="98e59-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e59-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="98e59-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="98e59-131">Имя приложения, которое поступило об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="98e59-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e59-132"><strong>Телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-133">идентификатора</span><span class="sxs-lookup"><span data-stu-id="98e59-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="98e59-134">Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</span><span class="sxs-lookup"><span data-stu-id="98e59-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e59-135"><strong>Сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-136">целое</span><span class="sxs-lookup"><span data-stu-id="98e59-136">int</span></span></p></td>
<td><p><span data-ttu-id="98e59-137">Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="98e59-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e59-138"><strong>Мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="98e59-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="98e59-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="98e59-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="98e59-140">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="98e59-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

