---
title: 'Lync Server 2013: конфигурация тестовой базы данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d57659c93aa42392f5408721157df1d14b56b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504106"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="085ef-102">Тестирование конфигурации базы данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="085ef-102">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="085ef-103">_**Последнее изменение темы:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="085ef-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="085ef-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="085ef-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="085ef-105">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="085ef-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="085ef-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="085ef-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="085ef-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="085ef-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="085ef-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="085ef-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="085ef-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins и иметь права администратора на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="085ef-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="085ef-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="085ef-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="085ef-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="085ef-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="085ef-112">Описание</span><span class="sxs-lookup"><span data-stu-id="085ef-112">Description</span></span>

<span data-ttu-id="085ef-113">Командлет **Test-CsDatabase** проверяет возможность подключения к одной или нескольким базам данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="085ef-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="085ef-114">При запуске командлет **Test-CsDatabase** считывает топологию Lync Server, пытается подключиться к соответствующим базам данных, а затем сообщает об успехе или неудаче каждой попытки.</span><span class="sxs-lookup"><span data-stu-id="085ef-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="085ef-115">Если подключение возможно, командлет также сообщит о такой информации, как имя базы данных, сведения о версии SQL Server, а также расположение любых установленных зеркальных баз данных.</span><span class="sxs-lookup"><span data-stu-id="085ef-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="085ef-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="085ef-116">Running the test</span></span>

<span data-ttu-id="085ef-117">Команда в примере 1 проверяет конфигурацию базы данных центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="085ef-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="085ef-118">В примере 2 проверяется все базы данных Lync Server, установленные на компьютере atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="085ef-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="085ef-p103">В примере 3 проверка проводится только для базы данных Archiving (Архив), установленной на компьютере atl-sql-001.litwareinc.com. Обратите внимание, что здесь используется параметр SqlInstanceName, который указывает экземпляр SQL Server (Archinst), где расположена база данных Archiving.</span><span class="sxs-lookup"><span data-stu-id="085ef-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="085ef-121">Команда, рассматриваемая в примере 4, проверяет базу данных, установленную на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="085ef-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="085ef-122">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="085ef-122">Determining success or failure</span></span>

<span data-ttu-id="085ef-123">Если подключение к базе данных настроено правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство "успешно", помеченное как **true**:</span><span class="sxs-lookup"><span data-stu-id="085ef-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="085ef-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="085ef-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="085ef-125">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="085ef-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="085ef-126">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="085ef-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="085ef-127">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="085ef-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="085ef-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="085ef-128">DatabaseName : xds</span></span>

<span data-ttu-id="085ef-129">Данных</span><span class="sxs-lookup"><span data-stu-id="085ef-129">DataSource :</span></span>

<span data-ttu-id="085ef-130">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-130">SQLServerVersion :</span></span>

<span data-ttu-id="085ef-131">Експектедверсион: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="085ef-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="085ef-132">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-132">InstalledVersion :</span></span>

<span data-ttu-id="085ef-133">Успешно: true</span><span class="sxs-lookup"><span data-stu-id="085ef-133">Succeed : True</span></span>

<span data-ttu-id="085ef-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="085ef-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="085ef-135">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="085ef-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="085ef-136">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="085ef-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="085ef-137">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="085ef-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="085ef-138">DatabaseName: LIS</span><span class="sxs-lookup"><span data-stu-id="085ef-138">DatabaseName : lis</span></span>

<span data-ttu-id="085ef-139">Данных</span><span class="sxs-lookup"><span data-stu-id="085ef-139">DataSource :</span></span>

<span data-ttu-id="085ef-140">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-140">SQLServerVersion :</span></span>

<span data-ttu-id="085ef-141">Експектедверсион: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="085ef-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="085ef-142">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-142">InstalledVersion :</span></span>

<span data-ttu-id="085ef-143">Успешно: true</span><span class="sxs-lookup"><span data-stu-id="085ef-143">Succeed : True</span></span>

<span data-ttu-id="085ef-144">Если база данных настроена правильно, но по-прежнему доступна, в поле успешно отображается **значение false**, а также предоставляются дополнительные предупреждения и сведения:</span><span class="sxs-lookup"><span data-stu-id="085ef-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="085ef-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="085ef-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="085ef-146">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="085ef-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="085ef-147">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="085ef-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="085ef-148">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="085ef-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="085ef-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="085ef-149">DatabaseName : xds</span></span>

<span data-ttu-id="085ef-150">Данных</span><span class="sxs-lookup"><span data-stu-id="085ef-150">DataSource :</span></span>

<span data-ttu-id="085ef-151">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-151">SQLServerVersion :</span></span>

<span data-ttu-id="085ef-152">Експектедверсион: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="085ef-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="085ef-153">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-153">InstalledVersion :</span></span>

<span data-ttu-id="085ef-154">Успешно: false</span><span class="sxs-lookup"><span data-stu-id="085ef-154">Succeed : False</span></span>

<span data-ttu-id="085ef-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="085ef-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="085ef-156">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="085ef-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="085ef-157">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="085ef-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="085ef-158">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="085ef-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="085ef-159">DatabaseName: LIS</span><span class="sxs-lookup"><span data-stu-id="085ef-159">DatabaseName : lis</span></span>

<span data-ttu-id="085ef-160">Данных</span><span class="sxs-lookup"><span data-stu-id="085ef-160">DataSource :</span></span>

<span data-ttu-id="085ef-161">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-161">SQLServerVersion :</span></span>

<span data-ttu-id="085ef-162">Експектедверсион: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="085ef-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="085ef-163">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="085ef-163">InstalledVersion :</span></span>

<span data-ttu-id="085ef-164">Успешно: false</span><span class="sxs-lookup"><span data-stu-id="085ef-164">Succeed : False</span></span>

<span data-ttu-id="085ef-165">Предупреждение: в Test-CsDatabase возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="085ef-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="085ef-166">Обратитесь к файлу журнала для</span><span class="sxs-lookup"><span data-stu-id="085ef-166">Consult the log file for a</span></span>

<span data-ttu-id="085ef-167">подробный анализ и проверка того, что устранены все ошибки (2) и предупреждения (0)</span><span class="sxs-lookup"><span data-stu-id="085ef-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="085ef-168">перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="085ef-168">before continuing.</span></span>

<span data-ttu-id="085ef-169">Предупреждение: подробные результаты можно найти по адресу:</span><span class="sxs-lookup"><span data-stu-id="085ef-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="085ef-170">"C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="085ef-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="085ef-171">04d593cce8e6.html ".</span><span class="sxs-lookup"><span data-stu-id="085ef-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="085ef-172">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="085ef-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="085ef-173">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsDatabase** :</span><span class="sxs-lookup"><span data-stu-id="085ef-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="085ef-174">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="085ef-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="085ef-175">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="085ef-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="085ef-176">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="085ef-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="085ef-177">Эта команда завершится с ошибками, если база данных неправильно настроена или еще не развернута.</span><span class="sxs-lookup"><span data-stu-id="085ef-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="085ef-178">См. также</span><span class="sxs-lookup"><span data-stu-id="085ef-178">See Also</span></span>


[<span data-ttu-id="085ef-179">Get — CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="085ef-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="085ef-180">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="085ef-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="085ef-181">Get — CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="085ef-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

