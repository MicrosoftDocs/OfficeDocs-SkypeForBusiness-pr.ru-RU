---
title: 'Lync Server 2013: Тестирование службы реплики'
description: 'Lync Server 2013: Тестирование службы реплики.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a61751b95115da3d6519f20f52262b7159ffcbfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556165"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="24bbd-103">Тестирование службы реплики в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24bbd-103">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24bbd-104">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="24bbd-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24bbd-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="24bbd-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="24bbd-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="24bbd-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bbd-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="24bbd-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="24bbd-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24bbd-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bbd-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="24bbd-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="24bbd-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="24bbd-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="24bbd-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="24bbd-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="24bbd-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="24bbd-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="24bbd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="24bbd-113">Description</span></span>

<span data-ttu-id="24bbd-114">Командлет **Test-CsReplica** проверяет, запущена ли служба реплики Lync Server 2013 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="24bbd-114">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="24bbd-115">Командлет **Test-CsReplica** выполняет такие задачи, как:</span><span class="sxs-lookup"><span data-stu-id="24bbd-115">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="24bbd-116">Проверка состояния агента Replicator и служб централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="24bbd-116">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="24bbd-117">Проверка того, что требуемые порты были открыты в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="24bbd-117">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="24bbd-118">Убедитесь, что у вас есть необходимые группы безопасности Active Directory и локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="24bbd-118">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="24bbd-119">Обратите внимание, что этот командлет должен выполняться локально.</span><span class="sxs-lookup"><span data-stu-id="24bbd-119">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="24bbd-120">То есть он должен выполняться на том же компьютере, на котором запущена служба реплики.</span><span class="sxs-lookup"><span data-stu-id="24bbd-120">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="24bbd-121">Нет параметров для запуска командлета **Test-CsReplica** на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="24bbd-121">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="24bbd-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="24bbd-122">Running the test</span></span>

<span data-ttu-id="24bbd-123">Команда, показанная в примере 1, тестирует службу реплики Lync Server 2013 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="24bbd-123">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="24bbd-124">В этом примере подробный параметр используется для гарантии того, что сведения о тесте, в том числе выработку результата теста, а также расположение отчета, созданного тестом, отображаются на экране.</span><span class="sxs-lookup"><span data-stu-id="24bbd-124">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="24bbd-125">Пример 2 представляет собой видоизмененную команду из примера 1.</span><span class="sxs-lookup"><span data-stu-id="24bbd-125">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="24bbd-126">В этом случае параметр Report включается для указания пути к папке и имени для отчета, созданного тестом.</span><span class="sxs-lookup"><span data-stu-id="24bbd-126">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="24bbd-127">Если путь к отчету не указан, ему будет присвоено автоматически созданное имя, которое выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="24bbd-127">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="24bbd-128">C: \\ Users \\ Administrator. litwareinc \\ AppData \\ Local \\ temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="24bbd-128">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="24bbd-129">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="24bbd-129">Determining success or failure</span></span>

<span data-ttu-id="24bbd-130">Вставьте сюда основную часть.</span><span class="sxs-lookup"><span data-stu-id="24bbd-130">Insert section body here.</span></span>

<span data-ttu-id="24bbd-131">VERBOSE: создание нового файла журнала "C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="24bbd-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="24bbd-132">VERBOSE: создание нового файла журнала "C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="24bbd-132">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="24bbd-133">VERBOSE: обработка "Test-CsReplica" успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="24bbd-133">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="24bbd-134">VERBOSE: подробные результаты можно найти на сайте "C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="24bbd-134">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="24bbd-135">VERBOSE: создание нового файла журнала</span><span class="sxs-lookup"><span data-stu-id="24bbd-135">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="24bbd-136">"C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="24bbd-136">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="24bbd-137">d3bd0e4a083.xml ".</span><span class="sxs-lookup"><span data-stu-id="24bbd-137">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="24bbd-138">VERBOSE: создание нового файла журнала</span><span class="sxs-lookup"><span data-stu-id="24bbd-138">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="24bbd-139">"C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="24bbd-139">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="24bbd-140">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="24bbd-140">d3bd0e4a083.html".</span></span>

<span data-ttu-id="24bbd-141">Предупреждение: Test-CsReplica не удалось выполнить.</span><span class="sxs-lookup"><span data-stu-id="24bbd-141">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="24bbd-142">Предупреждение: подробные результаты можно найти по адресу:</span><span class="sxs-lookup"><span data-stu-id="24bbd-142">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="24bbd-143">"C: \\ Пользователи \\ Тестовая папка \\ AppData \\ Local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="24bbd-143">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="24bbd-144">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="24bbd-144">d3bd0e4a083.html".</span></span>

<span data-ttu-id="24bbd-145">Test-CsReplica: не удалось выполнить команду: запрошенный доступ к реестру не</span><span class="sxs-lookup"><span data-stu-id="24bbd-145">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="24bbd-146">разрешенных.</span><span class="sxs-lookup"><span data-stu-id="24bbd-146">allowed.</span></span>

<span data-ttu-id="24bbd-147">В строке: 1 символ: 1</span><span class="sxs-lookup"><span data-stu-id="24bbd-147">At line:1 char:1</span></span>

<span data-ttu-id="24bbd-148">\+ Test-CsReplica подробных сведений</span><span class="sxs-lookup"><span data-stu-id="24bbd-148">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="24bbd-149">\+ Категоринфо: Инвалидоператион: (:) \[ Test-CsReplica \] , Security</span><span class="sxs-lookup"><span data-stu-id="24bbd-149">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="24bbd-150">Exception</span><span class="sxs-lookup"><span data-stu-id="24bbd-150">Exception</span></span>

<span data-ttu-id="24bbd-151">\+ Фулликуалифиедеррорид: Процессингфаилед, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="24bbd-151">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="24bbd-152">чения. тестрепликакмдлет</span><span class="sxs-lookup"><span data-stu-id="24bbd-152">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="24bbd-153">PS C: \\ \\ тестирование пользователей\></span><span class="sxs-lookup"><span data-stu-id="24bbd-153">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="24bbd-154">PS C: \\ Пользователи \\ проверяют \> Test-CsUcwaConference TargetFqdn "линктест. селфхост. Corp. M</span><span class="sxs-lookup"><span data-stu-id="24bbd-154">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="24bbd-155">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="24bbd-155">icrosoft.com"</span></span>

<span data-ttu-id="24bbd-156">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="24bbd-156">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="24bbd-157">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="24bbd-157">domain name (FQDN).</span></span> <span data-ttu-id="24bbd-158">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="24bbd-158">Using default Registrar port number.</span></span> <span data-ttu-id="24bbd-159">Возникновения</span><span class="sxs-lookup"><span data-stu-id="24bbd-159">Exception:</span></span>

<span data-ttu-id="24bbd-160">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="24bbd-160">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="24bbd-161">в</span><span class="sxs-lookup"><span data-stu-id="24bbd-161">at</span></span>

<span data-ttu-id="24bbd-162">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="24bbd-162">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="24bbd-163">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="24bbd-163">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="24bbd-164">Test-CsUcwaConference: нет тестового пользователя, назначенного для</span><span class="sxs-lookup"><span data-stu-id="24bbd-164">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="24bbd-165">\[LyncTest.SelfHost.Corp.Microsoft.com \] .</span><span class="sxs-lookup"><span data-stu-id="24bbd-165">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="24bbd-166">Проверьте конфигурацию тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="24bbd-166">Verify test user configuration.</span></span>

<span data-ttu-id="24bbd-167">В строке: 1 символ: 1</span><span class="sxs-lookup"><span data-stu-id="24bbd-167">At line:1 char:1</span></span>

<span data-ttu-id="24bbd-168">\+ Test-CsUcwaConference TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="24bbd-168">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="24bbd-169">\+ Категоринфо: Ресаурцеунаваилабле: (:) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="24bbd-169">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="24bbd-170">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="24bbd-170">, InvalidOperationException</span></span>

<span data-ttu-id="24bbd-171">\+ Фулликуалифиедеррорид: Нотфаундтестусерс, Microsoft. RTC. Management. синтезатор</span><span class="sxs-lookup"><span data-stu-id="24bbd-171">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="24bbd-172">Етиктрансактионс. Тестукваконференцекмдлет</span><span class="sxs-lookup"><span data-stu-id="24bbd-172">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="24bbd-173">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="24bbd-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="24bbd-174">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsReplica** :</span><span class="sxs-lookup"><span data-stu-id="24bbd-174">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="24bbd-175">Может возникнуть больше проблем с агентом Replicator и службами централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="24bbd-175">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="24bbd-176">Не удается открыть требуемые порты в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="24bbd-176">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="24bbd-177">Необходимые группы безопасности "Active Directory" и "локальный компьютер" могут не существовать.</span><span class="sxs-lookup"><span data-stu-id="24bbd-177">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

