---
title: Настройка регистрации вызовов и параметров качества взаимодействия
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 504c2221e9f8a3ef32e2cebbb792f5e03aef15c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="f7719-102">Настройка записи сведений о звонке и параметров качества обслуживания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7719-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7719-103">_**Тема последнего изменения:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="f7719-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="f7719-104">После связывания хранилища мониторинга с пулом переднего плана Настройте хранилище мониторинга, а затем установите и настройте службы отчетов SQL Server и Отслеживайте отчеты, которые можно управлять записью сведений о вызове (CDR) и качеством (QoE). наблюдение с помощью командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f7719-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="f7719-105">Командлеты командной консоли Lync Server позволяют включать и отключать мониторинг CDR и/или QoE для определенного сайта или для всего развертывания Lync Server. Это можно сделать с помощью команды.</span><span class="sxs-lookup"><span data-stu-id="f7719-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="f7719-106">При установке Microsoft Lync Server 2013 Вы также сможете установить предопределенную коллекцию глобальных параметров конфигурации для CDR и QoE.</span><span class="sxs-lookup"><span data-stu-id="f7719-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="f7719-107">В следующей таблице приведены значения по умолчанию для некоторых из наиболее часто используемых CDR параметров.</span><span class="sxs-lookup"><span data-stu-id="f7719-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7719-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="f7719-108">Property</span></span></th>
<th><span data-ttu-id="f7719-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f7719-109">Description</span></span></th>
<th><span data-ttu-id="f7719-110">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f7719-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7719-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="f7719-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="f7719-p103">Указывает, включен ли мониторинг регистрации вызовов (CDR). Если установлено значение True, то все записи CDR будут собираться и записываться в базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f7719-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="f7719-114">Верно</span><span class="sxs-lookup"><span data-stu-id="f7719-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7719-115">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="f7719-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="f7719-p104">Указывает, будут ли записи CDR периодически удаляться из базы данных. Если установлено значение True, то записи будут удаляться после периода времени, заданного в свойствах KeepCallDetailForDays (для записей CDR) и KeepErrorReportForDays (для ошибок CDR). Если параметр имеет значение False, то записи CDR будут сохраняться неопределенное время.</span><span class="sxs-lookup"><span data-stu-id="f7719-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="f7719-119">Верно</span><span class="sxs-lookup"><span data-stu-id="f7719-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7719-120">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="f7719-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="f7719-p105">Задает период в днях, в течение которого записи CDR будут сохраняться в базе данных; все записи старше заданного количества дней будут автоматически удаляться. Однако это будет происходить только в том случае, если включена очистка.</span><span class="sxs-lookup"><span data-stu-id="f7719-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="f7719-123">В качестве значения параметра KeepCallDetailForDays может быть установлено любое целое число от 1 до 2562 дней (приблизительно 7 лет).</span><span class="sxs-lookup"><span data-stu-id="f7719-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="f7719-124">60 дней</span><span class="sxs-lookup"><span data-stu-id="f7719-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7719-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="f7719-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="f7719-126">Указывает число дней, в течение которого сохраняются отчеты об ошибках CDR; все отчеты старше указанного числа дней будут автоматически удаляться.</span><span class="sxs-lookup"><span data-stu-id="f7719-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="f7719-127">Отчеты об ошибках CDR — это диагностические отчеты, которые отправляются клиентскими приложениями (например, Microsoft Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="f7719-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="f7719-128">В качестве значения этого свойства может быть установлено любое целое число от 1 до 2562 дней.</span><span class="sxs-lookup"><span data-stu-id="f7719-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="f7719-129">60 дней</span><span class="sxs-lookup"><span data-stu-id="f7719-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7719-130">Аналогично, значения по умолчанию для некоторых параметров QoE показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f7719-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7719-131">Свойство</span><span class="sxs-lookup"><span data-stu-id="f7719-131">Property</span></span></th>
<th><span data-ttu-id="f7719-132">Описание</span><span class="sxs-lookup"><span data-stu-id="f7719-132">Description</span></span></th>
<th><span data-ttu-id="f7719-133">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f7719-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7719-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="f7719-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="f7719-p107">Указывает, включен ли мониторинг QoE. Если установлено значение True, то все записи QoE будут собираться и записываться в базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f7719-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="f7719-137">Верно</span><span class="sxs-lookup"><span data-stu-id="f7719-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7719-138">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="f7719-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="f7719-p108">Указывает, будут ли записи QoE периодически удаляться из базы данных. Если установлено значение True, то записи будут удаляться после периода времени, заданного в свойстве KeepQoEDataForDays. Если параметр имеет значение False, то записи QoE будут сохраняться неопределенное время.</span><span class="sxs-lookup"><span data-stu-id="f7719-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="f7719-142">True</span><span class="sxs-lookup"><span data-stu-id="f7719-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7719-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="f7719-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="f7719-p109">Задает период в днях, в течение которого записи QoE будут сохраняться в базе данных; все записи старше заданного количества дней будут автоматически удаляться. Однако это будет происходить только в том случае, если включена очистка..</span><span class="sxs-lookup"><span data-stu-id="f7719-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="f7719-146">В качестве значения этого свойства может быть установлено любое целое число от 1 до 2562 дней.</span><span class="sxs-lookup"><span data-stu-id="f7719-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="f7719-147">60 дней</span><span class="sxs-lookup"><span data-stu-id="f7719-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7719-148">Если требуется изменить эти глобальные параметры, то это можно сделать с помощью командлетов Set-CsCdrConfiguration и Set-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f7719-148">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="f7719-149">Например, эта команда (выполнить из командной консоли Lync Server Management Shell) отключает CDR мониторинг в глобальной области. Это можно сделать, задав для свойства Енаблекдр значение false ($False):</span><span class="sxs-lookup"><span data-stu-id="f7719-149">For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="f7719-150">Следует отметить, что отключение мониторинга не отделяет хранилище данных наблюдения от интерфейсного пула, не удаляет его и никаким другим образом не влияет на тыловую базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f7719-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="f7719-151">Если вы используете командную консоль Lync Server для отключения CDR или QoE, вы временно не сможете собирать и архивировать данные мониторинга в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7719-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="f7719-152">Чтобы возобновить сбор и архивацию, например, данных CDR, достаточно просто вернуть значение True ($True) свойству EnableCDR:</span><span class="sxs-lookup"><span data-stu-id="f7719-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="f7719-153">Аналогично, следующая команда отключает очистку записей QoE на глобальном уровне:</span><span class="sxs-lookup"><span data-stu-id="f7719-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="f7719-p112">Помимо глобального уровня, параметры конфигурации CDR и QoE можно назначать на уровне сайта. Это обеспечивает дополнительную гибкость управления мониторингом; например, администратор может включить мониторинг CDR для сайта Redmond, но отключить мониторинг CDR для сайта Dublin. Для создания новых параметров конфигурации CDR на уровне сайта можно использовать команды, аналогичные следующей:</span><span class="sxs-lookup"><span data-stu-id="f7719-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="f7719-p113">Следует учитывать, что параметры, настроенные на уровне сайта, имеют преимущество перед параметрами, настроенными на глобальном уровне. Например, предположим, что мониторинг CDR включен на глобальном уровне, но отключен на уровне сайта для сайта Redmond. Это означает, что сведения регистрации вызовов для пользователей сайта Redmond не будут архивироваться. Однако для пользователей других сайтов (т.е. пользователей, которыми управляют глобальные настройки) сведения регистрации вызовов будут архивироваться.</span><span class="sxs-lookup"><span data-stu-id="f7719-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="f7719-161">Для создания новых параметров конфигурации QoE на уровне сайта можно использовать команды, аналогичные следующей:</span><span class="sxs-lookup"><span data-stu-id="f7719-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="f7719-162">Чтобы получить дополнительные сведения, в командной консоли Lync Server введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f7719-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

