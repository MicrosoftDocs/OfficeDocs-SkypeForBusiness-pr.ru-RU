---
title: 'Lync Server 2013: таблица таблица progressreport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aae907981e04d8966bb7eac4229232056d1004e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="7dd9a-102">Таблица Таблица progressreport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dd9a-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dd9a-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7dd9a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7dd9a-104">Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="7dd9a-105">Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="7dd9a-106">Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут относиться не к ошибкам, а к сообщениям, указывающим состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dd9a-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="7dd9a-107">Column</span></span></th>
<th><span data-ttu-id="7dd9a-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7dd9a-108">Data Type</span></span></th>
<th><span data-ttu-id="7dd9a-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="7dd9a-109">Key/Index</span></span></th>
<th><span data-ttu-id="7dd9a-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="7dd9a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dd9a-111"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7dd9a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7dd9a-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-114">Дата и время отчета об ошибках хода выполнения, который содержит этот отчет о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="7dd9a-115">Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7dd9a-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd9a-116"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-117">int</span><span class="sxs-lookup"><span data-stu-id="7dd9a-117">int</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-118">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="7dd9a-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-119">Идентификатор, используемый вместе с ErrorTime и ProgressReportSeq для однозначного определения отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="7dd9a-120">Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7dd9a-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd9a-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-122">int</span><span class="sxs-lookup"><span data-stu-id="7dd9a-122">int</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-123">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="7dd9a-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-124">Идентификатор отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-124">ID number that identifies the error report.</span></span> <span data-ttu-id="7dd9a-125">ErrorReporSeq используется вместе с ErrorTime для однозначного определения отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="7dd9a-126">Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7dd9a-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="7dd9a-127">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd9a-128"><strong>прогрессрепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-129">int</span><span class="sxs-lookup"><span data-stu-id="7dd9a-129">int</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-130">Primary</span><span class="sxs-lookup"><span data-stu-id="7dd9a-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-p105">Идентификатор отчета о ходе выполнения. Используется вместе с ErrorTime и ErrorReportSeq для однозначного определения отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd9a-133"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-134">int</span><span class="sxs-lookup"><span data-stu-id="7dd9a-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7dd9a-135">Диагностический идентификатор отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="7dd9a-136">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd9a-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-138">int</span><span class="sxs-lookup"><span data-stu-id="7dd9a-138">int</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-139">Правительства</span><span class="sxs-lookup"><span data-stu-id="7dd9a-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7dd9a-140">Сервер, который отправил отчет об ошибках (если отчет был отправлен из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="7dd9a-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="7dd9a-141">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> . Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd9a-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-143">int</span><span class="sxs-lookup"><span data-stu-id="7dd9a-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7dd9a-p107">Процесс Lync Server, к которому относится отчет. Дополнительные сведения см. в таблице приложений.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd9a-146"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-147">изображение</span><span class="sxs-lookup"><span data-stu-id="7dd9a-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7dd9a-148">Сведения о выполнении сохраняются в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="7dd9a-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="7dd9a-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="7dd9a-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd9a-150"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-151">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="7dd9a-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7dd9a-152">Уникальный идентификатор, который сопоставляет сведения о времени присоединения для разных компонентов, вовлеченных в конференцию.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="7dd9a-153">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd9a-154"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="7dd9a-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd9a-155">int</span><span class="sxs-lookup"><span data-stu-id="7dd9a-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7dd9a-156">Время (в миллисекундах) для присоединения к конференции конкретного компонента.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="7dd9a-157">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7dd9a-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

