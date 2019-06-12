---
title: 'Lync Server 2013: тестирование конференц-связи по УКВА'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b05b67f6f235cdcf3153149c9bd2373c30815d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="e3df6-102">Проверка конференц-связи УКВА в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3df6-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3df6-103">_**Тема последнего изменения:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="e3df6-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3df6-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="e3df6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e3df6-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="e3df6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3df6-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="e3df6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e3df6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3df6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3df6-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="e3df6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e3df6-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="e3df6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e3df6-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксукваконференце</strong> .</span><span class="sxs-lookup"><span data-stu-id="e3df6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="e3df6-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e3df6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e3df6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e3df6-112">Description</span></span>

<span data-ttu-id="e3df6-113">Командлет **Test-ксукваконференце** удостоверяется в том, что с помощью веб-интерфейса единой системы обмена сообщениями (Уква) пользователь может запланировать, присоединиться к Конференции и провести сетевую конференцию.</span><span class="sxs-lookup"><span data-stu-id="e3df6-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="e3df6-114">Для этого командлет использует службу веб-билета Lync Server для проверки подлинности двух тестовых пользователей и их регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3df6-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="e3df6-115">Затем командлет начнет конференцию с использованием учетных данных организатора и приглашает участника присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="e3df6-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="e3df6-116">После присоединения к собранию командлет **Test-ксукваконференце** удостоверяет, что пользователи могут выполнять такие действия, как обмен мгновенными сообщениями и объединением, а затем отключает конференцию и отменяет регистрацию двух тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="e3df6-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="e3df6-117">Запланированная Конференция также будет удалена после завершения теста.</span><span class="sxs-lookup"><span data-stu-id="e3df6-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="e3df6-118">Командлет **Test-ксукваконференце** также можно использовать, чтобы определить, могут ли анонимные пользователи присоединиться к онлайн-конференциям.</span><span class="sxs-lookup"><span data-stu-id="e3df6-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="e3df6-119">Обратите внимание, что командлет **Test-ксукваконференце** не следует запускать для пула Microsoft Lync Server 2010, если Уква не установлен в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="e3df6-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="e3df6-120">Если УКВА не установлен, вызов командлета **Test-ксукваконференце** завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="e3df6-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e3df6-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="e3df6-121">Running the test</span></span>

<span data-ttu-id="e3df6-122">Команда, показанная в примере 1, проверяет, может ли пользователь, который входит в состав Конференции УКВА в atl-cs-001.litwareinc.com пула, мог принимать участие в паре тестов.</span><span class="sxs-lookup"><span data-stu-id="e3df6-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e3df6-123">Обратите внимание, что эта команда завершится сбоем, если вы не предatl-CS-001.litwareinc.com пару пользователей теста конфигурации мониторинга работоспособности для.</span><span class="sxs-lookup"><span data-stu-id="e3df6-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e3df6-124">Команды, показанные в примере 2, проверяют возможности пары пользователей (плана litwareinc\\почтового и плана litwareinc\\кенмер) для участия в Уква Конференции.</span><span class="sxs-lookup"><span data-stu-id="e3df6-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="e3df6-125">Для этого в первой команде примера используется командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя почтового Вронский.</span><span class="sxs-lookup"><span data-stu-id="e3df6-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="e3df6-126">(Поскольку имя для входа, плана litwareinc\\почтового, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell требуется, чтобы администратор введет пароль для учетной записи почтового Вронский.) Результирующий объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="e3df6-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="e3df6-127">Вторая команда — это то же самое, что возвращает объект учетной записи Кен мер.</span><span class="sxs-lookup"><span data-stu-id="e3df6-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="e3df6-128">Если у вас есть два объекта учетных данных, третья команда в примере определяет, могут ли два пользователя принимать участие в конференц-связи УКВА.</span><span class="sxs-lookup"><span data-stu-id="e3df6-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="e3df6-129">Для выполнения этой задачи вызывается командлет **Test-ксукваконференце** , вместе со следующими параметрами: таржетфкдн (полное доменное имя пула регистраторов). Организерсипаддресс (SIP-адрес организатора собрания); Организеркредентиал (объект Windows PowerShell, который включает в себя учетные данные для этого пользователя); ПартиЦипантсипаддресс (SIP-адрес для другого тестового пользователя); и ПартиЦипанткредентиал (объект интерфейса командной строки Windows PowerShell, который включает в себя учетные данные для другого пользователя).</span><span class="sxs-lookup"><span data-stu-id="e3df6-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e3df6-130">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="e3df6-130">Determining success or failure</span></span>

<span data-ttu-id="e3df6-131">Если вы правильно настраиваете Конференц-связь, вы получите вывод примерно так, чтобы свойство Result пометило **"успешно".**</span><span class="sxs-lookup"><span data-stu-id="e3df6-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e3df6-132">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e3df6-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e3df6-133">Конечный URI: https://Линктест-SE. Линктест. Селфхост. Corp.</span><span class="sxs-lookup"><span data-stu-id="e3df6-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="e3df6-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="e3df6-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="e3df6-135">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="e3df6-135">Result : Success</span></span>

<span data-ttu-id="e3df6-136">Задержка: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="e3df6-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="e3df6-137">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="e3df6-137">Error Message :</span></span>

<span data-ttu-id="e3df6-138">Диагностик</span><span class="sxs-lookup"><span data-stu-id="e3df6-138">Diagnosis :</span></span>

<span data-ttu-id="e3df6-139">Если указанные пользователи не могут использовать конференц-связь, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="e3df6-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e3df6-140">Предупреждение: не удалось прочитать номер порта регистратора для заданного полного имени</span><span class="sxs-lookup"><span data-stu-id="e3df6-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="e3df6-141">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="e3df6-141">domain name (FQDN).</span></span> <span data-ttu-id="e3df6-142">С помощью номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3df6-142">Using default Registrar port number.</span></span> <span data-ttu-id="e3df6-143">Ошибка</span><span class="sxs-lookup"><span data-stu-id="e3df6-143">Exception:</span></span>

<span data-ttu-id="e3df6-144">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="e3df6-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="e3df6-145">скорость</span><span class="sxs-lookup"><span data-stu-id="e3df6-145">at</span></span>

<span data-ttu-id="e3df6-146">Microsoft. RTC. Management. Синсетиктрансактионс. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="e3df6-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="e3df6-147">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="e3df6-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="e3df6-148">Test-Ксукваконференце: нет тестового пользователя, назначенного для</span><span class="sxs-lookup"><span data-stu-id="e3df6-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="e3df6-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="e3df6-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="e3df6-150">Проверка конфигурации тестового пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3df6-150">Verify test user configuration.</span></span>

<span data-ttu-id="e3df6-151">В строке: 1 символ: 1</span><span class="sxs-lookup"><span data-stu-id="e3df6-151">At line:1 char:1</span></span>

<span data-ttu-id="e3df6-152">\+Test-Ксукваконференце-Таржетфкдн "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="e3df6-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="e3df6-153">\+Категоринфо: Ресаурцеунаваилабле: (:) \[Test-ксукваконференце\]</span><span class="sxs-lookup"><span data-stu-id="e3df6-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="e3df6-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="e3df6-154">, InvalidOperationException</span></span>

<span data-ttu-id="e3df6-155">\+Фулликуалифиедеррорид: Нотфаундтестусерс, Microsoft. RTC. Management. синтезатор</span><span class="sxs-lookup"><span data-stu-id="e3df6-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="e3df6-156">Етиктрансактионс. Тестукваконференцекмдлет</span><span class="sxs-lookup"><span data-stu-id="e3df6-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e3df6-157">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="e3df6-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="e3df6-158">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксукваконференце** :</span><span class="sxs-lookup"><span data-stu-id="e3df6-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="e3df6-159">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="e3df6-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e3df6-160">Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="e3df6-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e3df6-161">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="e3df6-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e3df6-162">Возможность проведения Конференции зависит от политики конференц-связи, назначенной пользователю, который организовал конференцию (в случае командлета **Test — ксукваконференце** , который является отправителем).</span><span class="sxs-lookup"><span data-stu-id="e3df6-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="e3df6-163">Если организатор не может включать мероприятия для совместной работы на своем собрании (например, если у его политики Конференции задано значение false), командлет **Test-ксукваконференце** завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="e3df6-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="e3df6-164">Эта команда завершается сбоем, если граничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="e3df6-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3df6-165">См. также</span><span class="sxs-lookup"><span data-stu-id="e3df6-165">See Also</span></span>


[<span data-ttu-id="e3df6-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="e3df6-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="e3df6-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="e3df6-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="e3df6-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="e3df6-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

