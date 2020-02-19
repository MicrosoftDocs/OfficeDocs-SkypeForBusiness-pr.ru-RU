---
title: 'Lync Server 2013: Установка Lync Server 2013 отчеты мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd30ff43d672e03747fdf58e2e333f62776fd40e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="b3522-102">Установка отчетов мониторинга Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3522-102">Installing Lync Server 2013 Monitoring Reports</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3522-103">_**Последнее изменение темы:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="b3522-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="b3522-104">Отчеты по мониторингу Microsoft Lync Server 2013 предоставляют обширную информацию о качестве и количестве сеансов связи, выполняемых в Организации.</span><span class="sxs-lookup"><span data-stu-id="b3522-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="b3522-105">Однако при установке Lync Server 2013 отчеты мониторинга не устанавливаются автоматически; Вместо этого необходимо устанавливать отчеты мониторинга отдельно и только после установки Lync Server на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b3522-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3522-p102">Рекомендуется устанавливать отчеты мониторинга на тот компьютер, на котором установлена база данных мониторинга. Это упрощает процесс назначения разрешений на доступ к отчетам: установка отчетов наблюдения на компьютер, на котором расположено хранилище данных наблюдения, означает, что не придется настраивать разрешения, которые позволяют базе данных на одном компьютере взаимодействовать со службами отчетов на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b3522-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="b3522-108">Отчеты мониторинга Lync Server включают более 30 отчетов, которые позволяют получить подробные сведения о конференциях, одноранговых сеансах обмена мгновенными сообщениями, регистрациях пользователей, приложении группы ответа и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b3522-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="b3522-109">Для версии 2013 отчеты мониторинга Lync Server включают ряд усовершенствований:</span><span class="sxs-lookup"><span data-stu-id="b3522-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="b3522-110">**Новые отчеты о качестве голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="b3522-110">**New voice quality reports**.</span></span> <span data-ttu-id="b3522-111">К этим новым отчетам относится [отчет по сравнению качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), который сравнивает качество связи между различными типами вызовов (например, между проводных и беспроводными вызовами); и [отчет о времени присоединения к Конференции в Lync Server 2013](lync-server-2013-conference-join-time-report.md), который предоставляет сведения, касающиеся времени, требуемого пользователям для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="b3522-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="b3522-112">**Улучшенные отчеты для анализа и диагностики видео связи и сеансов совместного использования приложений.**</span><span class="sxs-lookup"><span data-stu-id="b3522-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="b3522-113">[Сводный отчет по качеству мультимедиа в Lync server 2013](lync-server-2013-media-quality-summary-report.md) предоставляет способ анализа вызовов общего доступа к видео и приложениям, а в [отчете о производительности сервера в Lync Server 2013](lync-server-2013-server-performance-report.md) подробные сведения о производительности серверов, создающих эти вызовы.</span><span class="sxs-lookup"><span data-stu-id="b3522-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="b3522-114">Показатели общего доступа к видео и приложениям теперь также включены [в отчет по деталям однорангового сеанса в Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) и [подробный отчет о конференции в Lync Server 2013](lync-server-2013-conference-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="b3522-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="b3522-p106">**Улучшенная производительность отчетов**. В том числе более быстрое время ответа и получения данных, а также более быстрая и простая навигация по отчетам.</span><span class="sxs-lookup"><span data-stu-id="b3522-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="b3522-117">Дополнительные сведения об отдельных отчетах см. в документации по отчетам мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3522-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3522-118">Существует еще один новый отчет – QoE "подробные сведения о вызове", входящий в состав Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3522-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="b3522-119">Однако этот отчет существует главным образом для внутреннего использования и не предназначен для прямого доступа.</span><span class="sxs-lookup"><span data-stu-id="b3522-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="b3522-120">Существует два способа установки отчетов мониторинга Lync Server: вы можете использовать мастер развертывания Lync Server или можно использовать сценарий Windows PowerShell, входящий в установочные файлы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3522-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="b3522-121">Независимо от выбранного способа установки этих отчетов сначала необходимо убедиться в следующем.</span><span class="sxs-lookup"><span data-stu-id="b3522-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="b3522-122">Имеется право добавления роди базы данных в учетную запись пользователя в базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3522-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="b3522-p109">Имеется роль диспетчера содержимого в службах SQL Server Reporting Services. Эта роль дает право на развертывание отчетов в службах SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="b3522-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="b3522-125">Чтобы установить отчеты мониторинга с помощью мастера развертывания, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b3522-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="b3522-126">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b3522-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="b3522-127">В мастере развертывания нажмите команду **Deploy Monitoring Reports (Развернуть отчеты мониторинга)**, чтобы запустить мастер развертывания отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3522-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="b3522-p110">В мастере развертывания отчетов мониторинга на странице **указания базы данных мониторинга** убедитесь, что в раскрывающемся списке **Monitoring database (База данных мониторинга)** отображается полное доменное имя компьютера, на котором размещается хранилище данных наблюдения. (Если имеется несколько хранилищ данных наблюдения, то потребуется выбрать соответствующий сервер в этом раскрывающемся списке.) Убедитесь, что в поле **SQL Server Reporting Services (SSRS) instance (Экземпляр служб SQL Server Reporting Services)** отображается правильный экземпляр SQL Server (например, **atl-sql-001.litwareinc.com/archinst**), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b3522-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="b3522-130">На странице " **укажите учетные данные** " в поле **имя пользователя** введите доменное имя и имя пользователя учетной записи, которая будет использоваться при доступе к отчетам мониторинга (например, **\\litwareinc kenmyer**).</span><span class="sxs-lookup"><span data-stu-id="b3522-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="b3522-131">Если вы не используете этот формат (доменное\\имя пользователя), возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="b3522-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="b3522-132">Введите пароль для этой учетной записи в поле **Пароль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b3522-132">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="b3522-133">Обратите внимание, что для этой учетной записи не требуются никакие специальные права.</span><span class="sxs-lookup"><span data-stu-id="b3522-133">Note that no special rights are required for this account.</span></span> <span data-ttu-id="b3522-134">При завершении установки учетной записи автоматически будут предоставлены необходимые разрешения на вход и базу данных.</span><span class="sxs-lookup"><span data-stu-id="b3522-134">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="b3522-p113">На странице **указания группы только для чтения** в поле "Группа пользователя" введите имя группы безопасности, которой будет предоставлен доступ только для чтения в службах SQL Server Reporting Services. Например, чтобы предоставить администраторам доступ к отчетам только для чтения, введите **RTCUniversalReadOnlyAdmins**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b3522-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="b3522-138">На странице **выполнения команд** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b3522-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="b3522-139">Отчеты мониторинга также можно установить из командной консоли Lync Server, выполнив сценарий Деплойрепортс. ps1; Этот сценарий Windows PowerShell можно найти на установочном носителе Lync Server в папке \\установки\\репортингсетуп.</span><span class="sxs-lookup"><span data-stu-id="b3522-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="b3522-140">Чтобы установить отчеты мониторинга с помощью скрипта DeployReports.ps1, в командной консоли введите команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="b3522-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="b3522-141">Параметры, используемые в этой команде, описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b3522-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3522-142">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b3522-142">Parameter Name</span></span></th>
<th><span data-ttu-id="b3522-143">Обязательный</span><span class="sxs-lookup"><span data-stu-id="b3522-143">Required</span></span></th>
<th><span data-ttu-id="b3522-144">Описание</span><span class="sxs-lookup"><span data-stu-id="b3522-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3522-145">сторедусернаме</span><span class="sxs-lookup"><span data-stu-id="b3522-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="b3522-146">Да</span><span class="sxs-lookup"><span data-stu-id="b3522-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="b3522-147">Учетная запись пользователя (в формате домен\имя_пользователя) для доступа к хранилищу данных наблюдения; например:</span><span class="sxs-lookup"><span data-stu-id="b3522-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="b3522-148">Эта учетная запись должна иметь предварительно заданные разрешения на SQL Server и на службы SQL Server Reporting Services, в противном случае скрипт завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="b3522-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3522-149">сторедпассворд</span><span class="sxs-lookup"><span data-stu-id="b3522-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="b3522-150">Да</span><span class="sxs-lookup"><span data-stu-id="b3522-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="b3522-151">Пароль учетной записи пользователя для доступа к хранилищу данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="b3522-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3522-152">реадонлиграупнаме</span><span class="sxs-lookup"><span data-stu-id="b3522-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="b3522-153">Нет</span><span class="sxs-lookup"><span data-stu-id="b3522-153">No</span></span></p></td>
<td><p><span data-ttu-id="b3522-154">Домен или локальная группа безопасности, чьи члены получат доступ только для чтения отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3522-154">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="b3522-155">Обратите внимание, что если указанная группа не существует, то скрипт завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="b3522-155">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="b3522-156">Если позднее вы решите отозвать эти разрешения или предоставить разрешения на доступ другим пользователям или группам, то это можно будет сделать с помощью диспетчера отчетов служб SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="b3522-156">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3522-157">репортсклсерверинстанце</span><span class="sxs-lookup"><span data-stu-id="b3522-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="b3522-158">Нет</span><span class="sxs-lookup"><span data-stu-id="b3522-158">No</span></span></p></td>
<td><p><span data-ttu-id="b3522-p116">Экземпляр SQL Server, на котором размещаются службы отчетов. Экземпляр для служб отчетов следует указывать в виде полного доменного имени сервера отчетов, например:</span><span class="sxs-lookup"><span data-stu-id="b3522-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="b3522-161">Если этот параметр не указать, то скрипт будет предполагать, что службы отчетов размещаются в том же экземпляре SQL Server, что и база данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3522-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3522-162">мониторингдатабасеид</span><span class="sxs-lookup"><span data-stu-id="b3522-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="b3522-163">Нет</span><span class="sxs-lookup"><span data-stu-id="b3522-163">No</span></span></p></td>
<td><p><span data-ttu-id="b3522-p117">Удостоверение службы для базы данных мониторинга. Чтобы получить удостоверения для баз данных мониторинга, можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b3522-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b3522-166">После установки отчетов мониторинга необходимо использовать командлет Set-CsReportingConfiguration для настройки URL-адреса, используемого для доступа к этим отчетам.</span><span class="sxs-lookup"><span data-stu-id="b3522-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="b3522-167">Эту задачу можно выполнить из командной консоли Lync Server, выполнив следующую команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3522-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="b3522-168">Обратите внимание, что рекомендуется, но не обязательно, использовать протокол HTTPS при настройке URL-адреса отчетов:</span><span class="sxs-lookup"><span data-stu-id="b3522-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="b3522-p119">в предыдущей команде в свойстве ReportingUrl должен быть установлен URL-адрес диспетчера отчетов, используемый службами SQL Server 2008 R2 Reporting Services. Чтобы определить URL-адрес диспетчера отчетов, на компьютере с установленными службами отчетов SQL Server выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b3522-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="b3522-171">Нажмите кнопку "Пуск" и последовательно выберите пункты "Программы", "Microsoft SQL Server 2008 R2", "Средства настройки" и "Диспетчер конфигурации служб Reporting Services".</span><span class="sxs-lookup"><span data-stu-id="b3522-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="b3522-p120">В диалоговом окне "Соединение конфигурации служб Reporting Services" убедитесь, что в поле "Имя сервера" отображается имя компьютера со службами отчетов. Выберите экземпляр SQL Server в раскрывающемся списке "Экземпляр сервера отчетов" и нажмите кнопку "Подключить".</span><span class="sxs-lookup"><span data-stu-id="b3522-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="b3522-p121">В диспетчере конфигурации служб Reporting Services выберите "URL-адрес диспетчера отчетов". В области "URL-адрес диспетчера отчетов" должен появиться хотя бы один URL-адрес. Любой из появившихся URL-адресов можно использовать в качестве значения ReportingURL, хотя рекомендуется, чтобы этот ReportingUrl использовал протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b3522-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="b3522-177">Если для базы данных мониторинга настроена зеркальная база данных, необходимо также связать отчеты мониторинга с зеркальной базой данных.</span><span class="sxs-lookup"><span data-stu-id="b3522-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="b3522-178">Для получения дополнительных сведений ознакомьтесь со статьей [связь отчетов мониторинга с зеркальной базой данных в Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .</span><span class="sxs-lookup"><span data-stu-id="b3522-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

