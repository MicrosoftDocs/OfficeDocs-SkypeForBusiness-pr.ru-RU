---
title: 'Lync Server 2013: Проверка конфигурации базы данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805b62e234f7a5469d3af3677ba81478fb3abc8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="36c01-102">Проверка конфигурации базы данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c01-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36c01-103">_**Тема последнего изменения:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="36c01-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36c01-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="36c01-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="36c01-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="36c01-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36c01-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="36c01-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="36c01-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36c01-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36c01-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="36c01-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="36c01-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс и должны иметь права администратора на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36c01-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="36c01-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксдатабасе</strong> .</span><span class="sxs-lookup"><span data-stu-id="36c01-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="36c01-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36c01-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="36c01-112">Описание</span><span class="sxs-lookup"><span data-stu-id="36c01-112">Description</span></span>

<span data-ttu-id="36c01-113">Командлет **Test-ксдатабасе** проверяет подключение к одной или нескольким базам данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36c01-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="36c01-114">При запуске командлет **Test-ксдатабасе** считывает топологию Lync Server, пытается подключиться к соответствующим базам данных, а затем сообщает об успешном завершении или сбое каждой попытки.</span><span class="sxs-lookup"><span data-stu-id="36c01-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="36c01-115">Если подключение может быть установлено, командлет также сообщит такую информацию, как имя базы данных, сведения о версии SQL Server и расположение установленных зеркальных баз данных.</span><span class="sxs-lookup"><span data-stu-id="36c01-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="36c01-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="36c01-116">Running the test</span></span>

<span data-ttu-id="36c01-117">Команда, показанная в примере 1, проверяет конфигурацию базы данных Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="36c01-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="36c01-118">Пример 2: проверка всех баз данных Lync Server, установленных на компьютере atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="36c01-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="36c01-119">В примере 3 Проверка выполняется только для архивной базы данных, установленной на компьютере atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="36c01-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="36c01-120">Обратите внимание, что параметр Склинстанценаме включает экземпляр SQL Server (Арчинст), в котором находится база данных архивации.</span><span class="sxs-lookup"><span data-stu-id="36c01-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="36c01-121">Команда, показанная в примере 4, проверяет базы данных, установленные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="36c01-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="36c01-122">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="36c01-122">Determining success or failure</span></span>

<span data-ttu-id="36c01-123">Если подключение к базам данных настроено должным образом, вы получите такие данные, как, например, свойство успешно, помеченное как **Истина**:</span><span class="sxs-lookup"><span data-stu-id="36c01-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="36c01-124">Склсерверфкдн: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36c01-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="36c01-125">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="36c01-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="36c01-126">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="36c01-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="36c01-127">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="36c01-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="36c01-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="36c01-128">DatabaseName : xds</span></span>

<span data-ttu-id="36c01-129">Источников</span><span class="sxs-lookup"><span data-stu-id="36c01-129">DataSource :</span></span>

<span data-ttu-id="36c01-130">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-130">SQLServerVersion :</span></span>

<span data-ttu-id="36c01-131">Експектедверсион: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="36c01-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="36c01-132">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-132">InstalledVersion :</span></span>

<span data-ttu-id="36c01-133">Успешно: истина</span><span class="sxs-lookup"><span data-stu-id="36c01-133">Succeed : True</span></span>

<span data-ttu-id="36c01-134">Склсерверфкдн: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36c01-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="36c01-135">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="36c01-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="36c01-136">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="36c01-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="36c01-137">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="36c01-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="36c01-138">Имя базы: LIS</span><span class="sxs-lookup"><span data-stu-id="36c01-138">DatabaseName : lis</span></span>

<span data-ttu-id="36c01-139">Источников</span><span class="sxs-lookup"><span data-stu-id="36c01-139">DataSource :</span></span>

<span data-ttu-id="36c01-140">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-140">SQLServerVersion :</span></span>

<span data-ttu-id="36c01-141">Експектедверсион: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="36c01-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="36c01-142">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-142">InstalledVersion :</span></span>

<span data-ttu-id="36c01-143">Успешно: истина</span><span class="sxs-lookup"><span data-stu-id="36c01-143">Succeed : True</span></span>

<span data-ttu-id="36c01-144">Если база данных настроена правильно, но по-прежнему доступна, поле "успешно" будет отображаться как " **ложь**", а также будут указаны дополнительные предупреждения и сведения.</span><span class="sxs-lookup"><span data-stu-id="36c01-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="36c01-145">Склсерверфкдн: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36c01-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="36c01-146">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="36c01-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="36c01-147">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="36c01-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="36c01-148">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="36c01-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="36c01-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="36c01-149">DatabaseName : xds</span></span>

<span data-ttu-id="36c01-150">Источников</span><span class="sxs-lookup"><span data-stu-id="36c01-150">DataSource :</span></span>

<span data-ttu-id="36c01-151">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-151">SQLServerVersion :</span></span>

<span data-ttu-id="36c01-152">Експектедверсион: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="36c01-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="36c01-153">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-153">InstalledVersion :</span></span>

<span data-ttu-id="36c01-154">Успешно: ложь</span><span class="sxs-lookup"><span data-stu-id="36c01-154">Succeed : False</span></span>

<span data-ttu-id="36c01-155">Склсерверфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36c01-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="36c01-156">Склинстанценаме: RTC</span><span class="sxs-lookup"><span data-stu-id="36c01-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="36c01-157">Миррорсклсерверфкдн:</span><span class="sxs-lookup"><span data-stu-id="36c01-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="36c01-158">Миррорсклинстанценаме:</span><span class="sxs-lookup"><span data-stu-id="36c01-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="36c01-159">Имя базы: LIS</span><span class="sxs-lookup"><span data-stu-id="36c01-159">DatabaseName : lis</span></span>

<span data-ttu-id="36c01-160">Источников</span><span class="sxs-lookup"><span data-stu-id="36c01-160">DataSource :</span></span>

<span data-ttu-id="36c01-161">Склсерверверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-161">SQLServerVersion :</span></span>

<span data-ttu-id="36c01-162">Експектедверсион: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="36c01-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="36c01-163">Инсталледверсион:</span><span class="sxs-lookup"><span data-stu-id="36c01-163">InstalledVersion :</span></span>

<span data-ttu-id="36c01-164">Успешно: ложь</span><span class="sxs-lookup"><span data-stu-id="36c01-164">Succeed : False</span></span>

<span data-ttu-id="36c01-165">Предупреждение: при выполнении теста-Ксдатабасе возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="36c01-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="36c01-166">Просмотрите файл журнала для</span><span class="sxs-lookup"><span data-stu-id="36c01-166">Consult the log file for a</span></span>

<span data-ttu-id="36c01-167">подробный анализ и проверка того, что все ошибки (2) и предупреждения (0) рассмотрены.</span><span class="sxs-lookup"><span data-stu-id="36c01-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="36c01-168">перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="36c01-168">before continuing.</span></span>

<span data-ttu-id="36c01-169">Предупреждение: подробные результаты можно найти по адресу</span><span class="sxs-lookup"><span data-stu-id="36c01-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="36c01-170">"C:\\пользователи\\\\проверяют\\каталог\\AppData\\Local\\Temp 2 Test-ксдатабасе-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="36c01-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="36c01-171">04d593cce8e6. HTML ".</span><span class="sxs-lookup"><span data-stu-id="36c01-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="36c01-172">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="36c01-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="36c01-173">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксдатабасе** :</span><span class="sxs-lookup"><span data-stu-id="36c01-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="36c01-174">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="36c01-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="36c01-175">Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="36c01-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="36c01-176">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="36c01-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="36c01-177">Эта команда завершается сбоем, если база данных неправильно настроена или еще не развернута.</span><span class="sxs-lookup"><span data-stu-id="36c01-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36c01-178">См. также</span><span class="sxs-lookup"><span data-stu-id="36c01-178">See Also</span></span>


[<span data-ttu-id="36c01-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="36c01-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="36c01-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="36c01-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="36c01-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="36c01-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

