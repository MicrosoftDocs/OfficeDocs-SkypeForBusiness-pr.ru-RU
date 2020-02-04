---
title: 'Lync Server 2013: Проверка службы реплики'
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
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="44813-102">Проверка службы реплики в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44813-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44813-103">_**Тема последнего изменения:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="44813-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44813-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="44813-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="44813-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="44813-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44813-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="44813-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="44813-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44813-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44813-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="44813-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="44813-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="44813-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="44813-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксреплика</strong> .</span><span class="sxs-lookup"><span data-stu-id="44813-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="44813-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="44813-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="44813-112">Описание</span><span class="sxs-lookup"><span data-stu-id="44813-112">Description</span></span>

<span data-ttu-id="44813-113">Командлет **Test-ксреплика** проверяет, запущена ли служба реплики Lync Server 2013 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44813-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="44813-114">Командлет **Test-ксреплика** выполняет такие задачи, как:</span><span class="sxs-lookup"><span data-stu-id="44813-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="44813-115">Проверка состояния агента Replicator и службы агента централизованного ведения журнала</span><span class="sxs-lookup"><span data-stu-id="44813-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="44813-116">Проверка того, что нужные порты были открыты в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="44813-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="44813-117">Убедитесь в наличии необходимых групп безопасности Active Directory и локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="44813-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="44813-118">Обратите внимание, что этот командлет должен выполняться локально.</span><span class="sxs-lookup"><span data-stu-id="44813-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="44813-119">Это значит, что она должна быть запущена на том же компьютере, на котором запущена служба реплики.</span><span class="sxs-lookup"><span data-stu-id="44813-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="44813-120">Для запуска командлета **Test-ксреплика** с удаленным сервером не существует параметров.</span><span class="sxs-lookup"><span data-stu-id="44813-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="44813-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="44813-121">Running the test</span></span>

<span data-ttu-id="44813-122">Команда, показанная в примере 1, проверяет службу реплики Lync Server 2013 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44813-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="44813-123">В этом примере параметр Verbose используется для того, чтобы гарантировать, что сведения о тесте — в том числе в конечном итоге отказа или успешности теста, а также расположение отчета, созданного тестом — отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="44813-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="44813-124">Пример 2 — это вариант команды, показанный в примере 1.</span><span class="sxs-lookup"><span data-stu-id="44813-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="44813-125">В этом случае параметр отчета включает в себя путь к папке и имя для отчета, созданного с помощью теста.</span><span class="sxs-lookup"><span data-stu-id="44813-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="44813-126">Если не указать путь к отчету, ему будет автоматически сгенерировано такое имя, как:</span><span class="sxs-lookup"><span data-stu-id="44813-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="44813-127">C:\\пользователи\\администратор. плана litwareinc\\AppData\\Local\\temp\\1\\тест-CS-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. HTML</span><span class="sxs-lookup"><span data-stu-id="44813-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="44813-128">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="44813-128">Determining success or failure</span></span>

<span data-ttu-id="44813-129">Вставить текст раздела здесь.</span><span class="sxs-lookup"><span data-stu-id="44813-129">Insert section body here.</span></span>

<span data-ttu-id="44813-130">ПОДРОБНЫй: создание нового файла журнала "C:\\пользователи\\тестирование\\AppData\\Local\\temp\\Test-ксреплика-3cb066b3-dd23-411a-8932-99f01c0f940c. XML".</span><span class="sxs-lookup"><span data-stu-id="44813-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="44813-131">ПОДРОБНЫй: создание нового файла журнала "C:\\пользователи\\тестирование\\AppData\\Local\\temp\\Test-ксреплика-3cb066b3-dd23-411a-8932-99f01c0f940c. XML".</span><span class="sxs-lookup"><span data-stu-id="44813-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="44813-132">ПОДРОБНОе сообщение: обработка "Test-Ксреплика" успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="44813-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="44813-133">ПОДРОБНЫй: подробные результаты можно найти на странице "C:\\пользователи\\тестирование\\AppData\\Local\\temp\\Test-ксреплика-3cb066b3-dd23-411a-8932-99f01c0f940c. XML".</span><span class="sxs-lookup"><span data-stu-id="44813-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="44813-134">ПОДРОБНЫй: создание нового файла журнала</span><span class="sxs-lookup"><span data-stu-id="44813-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="44813-135">"C:\\пользователи\\\\проверяют\\каталог\\AppData\\Local\\Temp 2 Test-ксреплика-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="44813-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="44813-136">d3bd0e4a083. XML ".</span><span class="sxs-lookup"><span data-stu-id="44813-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="44813-137">ПОДРОБНЫй: создание нового файла журнала</span><span class="sxs-lookup"><span data-stu-id="44813-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="44813-138">"C:\\пользователи\\\\проверяют\\каталог\\AppData\\Local\\Temp 2 Test-ксреплика-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="44813-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="44813-139">d3bd0e4a083. HTML ".</span><span class="sxs-lookup"><span data-stu-id="44813-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="44813-140">Предупреждение: Test-Ксреплика не удалось.</span><span class="sxs-lookup"><span data-stu-id="44813-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="44813-141">Предупреждение: подробные результаты можно найти по адресу</span><span class="sxs-lookup"><span data-stu-id="44813-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="44813-142">"C:\\пользователи\\\\проверяют\\каталог\\AppData\\Local\\Temp 2 Test-ксреплика-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="44813-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="44813-143">d3bd0e4a083. HTML ".</span><span class="sxs-lookup"><span data-stu-id="44813-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="44813-144">Test-Ксреплика: сбой при выполнении команды: запрошенный доступ к реестру не</span><span class="sxs-lookup"><span data-stu-id="44813-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="44813-145">использоваться.</span><span class="sxs-lookup"><span data-stu-id="44813-145">allowed.</span></span>

<span data-ttu-id="44813-146">В строке: 1 символ: 1</span><span class="sxs-lookup"><span data-stu-id="44813-146">At line:1 char:1</span></span>

<span data-ttu-id="44813-147">\+Test-Ксреплика-verbose</span><span class="sxs-lookup"><span data-stu-id="44813-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="44813-148">\+Категоринфо: Инвалидоператион: (:) \[Test-ксреплика\], безопасность</span><span class="sxs-lookup"><span data-stu-id="44813-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="44813-149">Ошибка</span><span class="sxs-lookup"><span data-stu-id="44813-149">Exception</span></span>

<span data-ttu-id="44813-150">\+Фулликуалифиедеррорид: Процессингфаилед, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="44813-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="44813-151">чения. тестрепликакмдлет</span><span class="sxs-lookup"><span data-stu-id="44813-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="44813-152">PS C:\\Проверка\\пользователей\></span><span class="sxs-lookup"><span data-stu-id="44813-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="44813-153">PS C:\\пользователи\\тестирование\> тест-Ксукваконференце-Таржетфкдн "Линктест. селфхост. Corp. M</span><span class="sxs-lookup"><span data-stu-id="44813-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="44813-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="44813-154">icrosoft.com"</span></span>

<span data-ttu-id="44813-155">Предупреждение: не удалось прочитать номер порта регистратора для заданного полного имени</span><span class="sxs-lookup"><span data-stu-id="44813-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="44813-156">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="44813-156">domain name (FQDN).</span></span> <span data-ttu-id="44813-157">С помощью номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44813-157">Using default Registrar port number.</span></span> <span data-ttu-id="44813-158">Ошибка</span><span class="sxs-lookup"><span data-stu-id="44813-158">Exception:</span></span>

<span data-ttu-id="44813-159">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="44813-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="44813-160">скорость</span><span class="sxs-lookup"><span data-stu-id="44813-160">at</span></span>

<span data-ttu-id="44813-161">Microsoft. RTC. Management. Синсетиктрансактионс. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="44813-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="44813-162">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="44813-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="44813-163">Test-Ксукваконференце: нет тестового пользователя, назначенного для</span><span class="sxs-lookup"><span data-stu-id="44813-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="44813-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="44813-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="44813-165">Проверка конфигурации тестового пользователя.</span><span class="sxs-lookup"><span data-stu-id="44813-165">Verify test user configuration.</span></span>

<span data-ttu-id="44813-166">В строке: 1 символ: 1</span><span class="sxs-lookup"><span data-stu-id="44813-166">At line:1 char:1</span></span>

<span data-ttu-id="44813-167">\+Test-Ксукваконференце-Таржетфкдн "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="44813-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="44813-168">\+Категоринфо: Ресаурцеунаваилабле: (:) \[Test-ксукваконференце\]</span><span class="sxs-lookup"><span data-stu-id="44813-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="44813-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="44813-169">, InvalidOperationException</span></span>

<span data-ttu-id="44813-170">\+Фулликуалифиедеррорид: Нотфаундтестусерс, Microsoft. RTC. Management. синтезатор</span><span class="sxs-lookup"><span data-stu-id="44813-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="44813-171">Етиктрансактионс. Тестукваконференцекмдлет</span><span class="sxs-lookup"><span data-stu-id="44813-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="44813-172">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="44813-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="44813-173">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксреплика** :</span><span class="sxs-lookup"><span data-stu-id="44813-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="44813-174">Возможно, возникла проблема с агентом тиражирования и службами агента централизованного ведения журнала</span><span class="sxs-lookup"><span data-stu-id="44813-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="44813-175">Возможно, требуемые порты не открыты в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="44813-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="44813-176">Возможно, не существует необходимая группа безопасности Active Directory и локального компьютера</span><span class="sxs-lookup"><span data-stu-id="44813-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

