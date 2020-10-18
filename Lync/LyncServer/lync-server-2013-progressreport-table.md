---
title: 'Lync Server 2013: таблица таблица progressreport'
description: 'Lync Server 2013: таблица таблица progressreport.'
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
ms.openlocfilehash: d36ee2ab75410ea2462da4b647ef5b45afefb1bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579825"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="75c43-103">Таблица Таблица progressreport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75c43-103">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75c43-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="75c43-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="75c43-105">Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса.</span><span class="sxs-lookup"><span data-stu-id="75c43-105">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="75c43-106">Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей.</span><span class="sxs-lookup"><span data-stu-id="75c43-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="75c43-107">Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут относиться не к ошибкам, а к сообщениям, указывающим состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="75c43-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75c43-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="75c43-108">Column</span></span></th>
<th><span data-ttu-id="75c43-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="75c43-109">Data Type</span></span></th>
<th><span data-ttu-id="75c43-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="75c43-110">Key/Index</span></span></th>
<th><span data-ttu-id="75c43-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="75c43-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75c43-112"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-113">datetime</span><span class="sxs-lookup"><span data-stu-id="75c43-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="75c43-114">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="75c43-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="75c43-115">Дата и время отчета об ошибках хода выполнения, который содержит этот отчет о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="75c43-115">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="75c43-116">Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="75c43-116">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c43-117"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-117"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-118">int</span><span class="sxs-lookup"><span data-stu-id="75c43-118">int</span></span></p></td>
<td><p><span data-ttu-id="75c43-119">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="75c43-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="75c43-120">Идентификатор, используемый вместе с ErrorTime и ProgressReportSeq для однозначного определения отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="75c43-120">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="75c43-121">Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="75c43-121">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c43-122"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-122"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-123">int</span><span class="sxs-lookup"><span data-stu-id="75c43-123">int</span></span></p></td>
<td><p><span data-ttu-id="75c43-124">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="75c43-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="75c43-125">Идентификатор отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="75c43-125">ID number that identifies the error report.</span></span> <span data-ttu-id="75c43-126">ErrorReporSeq используется вместе с ErrorTime для однозначного определения отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="75c43-126">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="75c43-127">Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="75c43-127">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="75c43-128">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75c43-128">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c43-129"><strong>прогрессрепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-129"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-130">int</span><span class="sxs-lookup"><span data-stu-id="75c43-130">int</span></span></p></td>
<td><p><span data-ttu-id="75c43-131">Primary</span><span class="sxs-lookup"><span data-stu-id="75c43-131">Primary</span></span></p></td>
<td><p><span data-ttu-id="75c43-p105">Идентификатор отчета о ходе выполнения. Используется вместе с ErrorTime и ErrorReportSeq для однозначного определения отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="75c43-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c43-134"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-134"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-135">int</span><span class="sxs-lookup"><span data-stu-id="75c43-135">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="75c43-136">Диагностический идентификатор отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="75c43-136">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="75c43-137">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75c43-137">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c43-138"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-138"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-139">int</span><span class="sxs-lookup"><span data-stu-id="75c43-139">int</span></span></p></td>
<td><p><span data-ttu-id="75c43-140">Правительства</span><span class="sxs-lookup"><span data-stu-id="75c43-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="75c43-141">Сервер, который отправил отчет об ошибках (если отчет был отправлен из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="75c43-141">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="75c43-142">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> . Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75c43-142">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c43-143"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-143"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-144">int</span><span class="sxs-lookup"><span data-stu-id="75c43-144">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="75c43-p107">Процесс Lync Server, к которому относится отчет. Дополнительные сведения см. в таблице приложений.</span><span class="sxs-lookup"><span data-stu-id="75c43-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c43-147"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-147"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-148">изображение</span><span class="sxs-lookup"><span data-stu-id="75c43-148">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="75c43-149">Сведения о выполнении сохраняются в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="75c43-149">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="75c43-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="75c43-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c43-151"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-151"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-152">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="75c43-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="75c43-153">Уникальный идентификатор, который сопоставляет сведения о времени присоединения для разных компонентов, вовлеченных в конференцию.</span><span class="sxs-lookup"><span data-stu-id="75c43-153">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="75c43-154">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75c43-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c43-155"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="75c43-155"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75c43-156">int</span><span class="sxs-lookup"><span data-stu-id="75c43-156">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="75c43-157">Время (в миллисекундах) для присоединения к конференции конкретного компонента.</span><span class="sxs-lookup"><span data-stu-id="75c43-157">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="75c43-158">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75c43-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

