---
title: 'Lync Server 2013: конфигурация тестовой базы данных'
description: 'Lync Server 2013: тестирование конфигурации базы данных.'
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
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560685"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="174a1-103">Тестирование конфигурации базы данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="174a1-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="174a1-104">_**Последнее изменение темы:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="174a1-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="174a1-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="174a1-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="174a1-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="174a1-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="174a1-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="174a1-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="174a1-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="174a1-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="174a1-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="174a1-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="174a1-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins и иметь права администратора на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="174a1-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="174a1-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="174a1-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="174a1-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="174a1-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="174a1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="174a1-113">Description</span></span>

<span data-ttu-id="174a1-114">Командлет **Test-CsDatabase** проверяет возможность подключения к одной или нескольким базам данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="174a1-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="174a1-115">При запуске командлет **Test-CsDatabase** считывает топологию Lync Server, пытается подключиться к соответствующим базам данных, а затем сообщает об успехе или неудаче каждой попытки.</span><span class="sxs-lookup"><span data-stu-id="174a1-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="174a1-116">Если подключение возможно, командлет также сообщит о такой информации, как имя базы данных, сведения о версии SQL Server, а также расположение любых установленных зеркальных баз данных.</span><span class="sxs-lookup"><span data-stu-id="174a1-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="174a1-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="174a1-117">Running the test</span></span>

<span data-ttu-id="174a1-118">Команда в примере 1 проверяет конфигурацию базы данных центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="174a1-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="174a1-119">В примере 2 проверяется все базы данных Lync Server, установленные на компьютере atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="174a1-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="174a1-p103">В примере 3 проверка проводится только для базы данных Archiving (Архив), установленной на компьютере atl-sql-001.litwareinc.com. Обратите внимание, что здесь используется параметр SqlInstanceName, который указывает экземпляр SQL Server (Archinst), где расположена база данных Archiving.</span><span class="sxs-lookup"><span data-stu-id="174a1-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="174a1-122">Команда, рассматриваемая в примере 4, проверяет базу данных, установленную на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="174a1-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="174a1-123">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="174a1-123">Determining success or failure</span></span>

<span data-ttu-id="174a1-124">Если подключение к базе данных настроено правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство "успешно", помеченное как **true**:</span><span class="sxs-lookup"><span data-stu-id="174a1-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="174a1-125">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="174a1-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="174a1-126">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="174a1-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="174a1-127">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="174a1-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="174a1-128">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="174a1-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="174a1-129">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="174a1-129">DatabaseName : xds</span></span>

<span data-ttu-id="174a1-130">Данных</span><span class="sxs-lookup"><span data-stu-id="174a1-130">DataSource :</span></span>

<span data-ttu-id="174a1-131">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-131">SQLServerVersion :</span></span>

<span data-ttu-id="174a1-132">Експектедверсион: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="174a1-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="174a1-133">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-133">InstalledVersion :</span></span>

<span data-ttu-id="174a1-134">Успешно: true</span><span class="sxs-lookup"><span data-stu-id="174a1-134">Succeed : True</span></span>

<span data-ttu-id="174a1-135">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="174a1-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="174a1-136">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="174a1-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="174a1-137">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="174a1-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="174a1-138">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="174a1-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="174a1-139">DatabaseName: LIS</span><span class="sxs-lookup"><span data-stu-id="174a1-139">DatabaseName : lis</span></span>

<span data-ttu-id="174a1-140">Данных</span><span class="sxs-lookup"><span data-stu-id="174a1-140">DataSource :</span></span>

<span data-ttu-id="174a1-141">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-141">SQLServerVersion :</span></span>

<span data-ttu-id="174a1-142">Експектедверсион: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="174a1-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="174a1-143">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-143">InstalledVersion :</span></span>

<span data-ttu-id="174a1-144">Успешно: true</span><span class="sxs-lookup"><span data-stu-id="174a1-144">Succeed : True</span></span>

<span data-ttu-id="174a1-145">Если база данных настроена правильно, но по-прежнему доступна, в поле успешно отображается **значение false**, а также предоставляются дополнительные предупреждения и сведения:</span><span class="sxs-lookup"><span data-stu-id="174a1-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="174a1-146">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="174a1-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="174a1-147">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="174a1-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="174a1-148">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="174a1-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="174a1-149">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="174a1-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="174a1-150">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="174a1-150">DatabaseName : xds</span></span>

<span data-ttu-id="174a1-151">Данных</span><span class="sxs-lookup"><span data-stu-id="174a1-151">DataSource :</span></span>

<span data-ttu-id="174a1-152">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-152">SQLServerVersion :</span></span>

<span data-ttu-id="174a1-153">Експектедверсион: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="174a1-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="174a1-154">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-154">InstalledVersion :</span></span>

<span data-ttu-id="174a1-155">Успешно: false</span><span class="sxs-lookup"><span data-stu-id="174a1-155">Succeed : False</span></span>

<span data-ttu-id="174a1-156">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="174a1-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="174a1-157">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="174a1-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="174a1-158">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="174a1-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="174a1-159">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="174a1-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="174a1-160">DatabaseName: LIS</span><span class="sxs-lookup"><span data-stu-id="174a1-160">DatabaseName : lis</span></span>

<span data-ttu-id="174a1-161">Данных</span><span class="sxs-lookup"><span data-stu-id="174a1-161">DataSource :</span></span>

<span data-ttu-id="174a1-162">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-162">SQLServerVersion :</span></span>

<span data-ttu-id="174a1-163">Експектедверсион: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="174a1-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="174a1-164">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="174a1-164">InstalledVersion :</span></span>

<span data-ttu-id="174a1-165">Успешно: false</span><span class="sxs-lookup"><span data-stu-id="174a1-165">Succeed : False</span></span>

<span data-ttu-id="174a1-166">Предупреждение: в Test-CsDatabase возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="174a1-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="174a1-167">Обратитесь к файлу журнала для</span><span class="sxs-lookup"><span data-stu-id="174a1-167">Consult the log file for a</span></span>

<span data-ttu-id="174a1-168">подробный анализ и проверка того, что устранены все ошибки (2) и предупреждения (0)</span><span class="sxs-lookup"><span data-stu-id="174a1-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="174a1-169">перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="174a1-169">before continuing.</span></span>

<span data-ttu-id="174a1-170">Предупреждение: подробные результаты можно найти по адресу:</span><span class="sxs-lookup"><span data-stu-id="174a1-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="174a1-171">"C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="174a1-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="174a1-172">04d593cce8e6.html ".</span><span class="sxs-lookup"><span data-stu-id="174a1-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="174a1-173">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="174a1-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="174a1-174">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsDatabase** :</span><span class="sxs-lookup"><span data-stu-id="174a1-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="174a1-175">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="174a1-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="174a1-176">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="174a1-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="174a1-177">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="174a1-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="174a1-178">Эта команда завершится с ошибками, если база данных неправильно настроена или еще не развернута.</span><span class="sxs-lookup"><span data-stu-id="174a1-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="174a1-179">См. также</span><span class="sxs-lookup"><span data-stu-id="174a1-179">See Also</span></span>


[<span data-ttu-id="174a1-180">Get — CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="174a1-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="174a1-181">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="174a1-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="174a1-182">Get — CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="174a1-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

