---
title: 'Lync Server 2013: таблица ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="e8117-102">Таблица ProgressReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8117-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8117-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e8117-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e8117-104">Отчеты о состоянии основываются на данных, отправленных клиентом в базу данных после завершения вызова или сеанса.</span><span class="sxs-lookup"><span data-stu-id="e8117-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="e8117-105">Отчеты о ходе выполнения будут записываться только для звонков и сеансов, которые определяет Lync Server 2013, может быть полезен в целях диагностики.</span><span class="sxs-lookup"><span data-stu-id="e8117-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="e8117-106">Поля Еррортиме, Ерроррепортсек и Прогрессрепортсек не обязательно ссылаются на ошибки, а также на сообщения, указывающие на состояние вызовов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="e8117-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8117-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="e8117-107">Column</span></span></th>
<th><span data-ttu-id="e8117-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e8117-108">Data Type</span></span></th>
<th><span data-ttu-id="e8117-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="e8117-109">Key/Index</span></span></th>
<th><span data-ttu-id="e8117-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="e8117-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8117-111"><strong>Еррортиме</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e8117-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e8117-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e8117-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8117-114">Дата и время отчета об ошибках хода выполнения, который включает этот отчет о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8117-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="e8117-115">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-errorreport-table.md">таблицей ерроррепорт в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e8117-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8117-116"><strong>Еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-117">целое</span><span class="sxs-lookup"><span data-stu-id="e8117-117">int</span></span></p></td>
<td><p><span data-ttu-id="e8117-118">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e8117-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8117-119">ИДЕНТИФИКАЦИОНный номер, используемый в сочетании с Еррортиме, Прогрессрепортсек для уникальной идентификации отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8117-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="e8117-120">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-errorreport-table.md">таблицей ерроррепорт в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e8117-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8117-121"><strong>Ерроррепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-122">целое</span><span class="sxs-lookup"><span data-stu-id="e8117-122">int</span></span></p></td>
<td><p><span data-ttu-id="e8117-123">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e8117-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8117-124">ИДЕНТИФИКАЦИОНный номер, идентифицирующий отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e8117-124">ID number that identifies the error report.</span></span> <span data-ttu-id="e8117-125">Ерроррепорсек используется в сочетании с Еррортиме для уникальной идентификации отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e8117-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="e8117-126">Дополнительные сведения приведены <a href="lync-server-2013-errorreport-table.md">в таблице ерроррепорт в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8117-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="e8117-127">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8117-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8117-128"><strong>Прогрессрепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-129">целое</span><span class="sxs-lookup"><span data-stu-id="e8117-129">int</span></span></p></td>
<td><p><span data-ttu-id="e8117-130">Primary</span><span class="sxs-lookup"><span data-stu-id="e8117-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="e8117-131">ИДЕНТИФИКАЦИОНный номер для идентификации отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8117-131">ID number to identify the progress report.</span></span> <span data-ttu-id="e8117-132">Используется совместно с Еррортиме и Ерроррепортсек для уникальной идентификации отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8117-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8117-133"><strong>Мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-134">целое</span><span class="sxs-lookup"><span data-stu-id="e8117-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8117-135">Идентификатор диагностики отчета о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8117-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="e8117-136">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8117-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8117-137"><strong>Источника</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-138">целое</span><span class="sxs-lookup"><span data-stu-id="e8117-138">int</span></span></p></td>
<td><p><span data-ttu-id="e8117-139">Другом</span><span class="sxs-lookup"><span data-stu-id="e8117-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8117-140">Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="e8117-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="e8117-141">Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> . Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8117-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8117-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-143">целое</span><span class="sxs-lookup"><span data-stu-id="e8117-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8117-144">Процесс Lync Server, к которому относится отчет.</span><span class="sxs-lookup"><span data-stu-id="e8117-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="e8117-145">Для получения дополнительных сведений ознакомьтесь с таблицей Application.</span><span class="sxs-lookup"><span data-stu-id="e8117-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8117-146"><strong>Подробности</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-147">изображение</span><span class="sxs-lookup"><span data-stu-id="e8117-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8117-148">Сведения о отчете о состоянии, сохраняемые в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e8117-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="e8117-149">Cast (CAST (данные в формате varbinary (max)) AS varchar (max))</span><span class="sxs-lookup"><span data-stu-id="e8117-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8117-150"><strong>Телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-151">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="e8117-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8117-152">Уникальный идентификатор, который соответствует сведениям о времени соединения для различных компонентов, участвующих в Конференции.</span><span class="sxs-lookup"><span data-stu-id="e8117-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="e8117-153">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8117-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8117-154"><strong>Сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="e8117-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e8117-155">целое</span><span class="sxs-lookup"><span data-stu-id="e8117-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8117-156">Время (в миллисекундах), в течение которого конкретный компонент присоединяется к Конференции.</span><span class="sxs-lookup"><span data-stu-id="e8117-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="e8117-157">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8117-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

