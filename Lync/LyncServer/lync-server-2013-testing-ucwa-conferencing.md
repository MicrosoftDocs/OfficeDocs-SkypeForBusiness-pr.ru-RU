---
title: 'Lync Server 2013: тестирование конференц-связи по UCWA'
description: 'Lync Server 2013: тестирование конференц-связи по UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f88a683abb67d55211422fc4dcf45fc1d5c966
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556095"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="3a0db-103">Тестирование конференц-связи UCWA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a0db-103">Testing UCWA conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a0db-104">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="3a0db-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a0db-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="3a0db-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3a0db-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="3a0db-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a0db-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="3a0db-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3a0db-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a0db-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a0db-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="3a0db-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3a0db-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3a0db-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3a0db-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsUcwaConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="3a0db-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="3a0db-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3a0db-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3a0db-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3a0db-113">Description</span></span>

<span data-ttu-id="3a0db-114">Командлет **Test-CsUcwaConference** проверяет, может ли пользователь, запланировать, присоединиться к Конференции, а затем провести интерактивную конференцию с помощью веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="3a0db-114">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="3a0db-115">Для этого командлет использует службу веб-билета Lync Server для проверки подлинности двух тестовых пользователей и их регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a0db-115">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="3a0db-116">Командлет затем запускает конференцию с помощью учетных данных организатора и приглашает участника присоединиться к встрече.</span><span class="sxs-lookup"><span data-stu-id="3a0db-116">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="3a0db-117">После подключения к собранию командлет **Test-CsUcwaConference** проверяет, могут ли пользователи выполнять такие действия, как обмен мгновенными сообщениями и проведение пулов, а затем отключает конференцию и отменяет регистрацию двух тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a0db-117">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="3a0db-118">Запланированная Конференция также будет удалена после завершения теста.</span><span class="sxs-lookup"><span data-stu-id="3a0db-118">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="3a0db-119">Командлет **Test-CsUcwaConference** также можно использовать, чтобы определить, могут ли анонимные пользователи присоединяться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="3a0db-119">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="3a0db-120">Обратите внимание на то, что командлет **Test-CsUcwaConference** не следует запускать для пула Microsoft Lync Server 2010, если UCWA не установлен в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="3a0db-120">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="3a0db-121">Если UCWA не установлен, вызов командлета **Test-CsUcwaConference** завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="3a0db-121">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3a0db-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="3a0db-122">Running the test</span></span>

<span data-ttu-id="3a0db-p104">Команда, показанная в Примере 1 проверяет возможность для пары тестовых пользователей принимать участие в конференции UCWA на пуле atl-cs-001.litwareinc.com. Обратите внимание, что эта команда не будет выполнена успешно, если заранее не определены тестовые пользователи конфигурации мониторинга состояния для atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3a0db-p104">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3a0db-125">Команды, показанные в примере 2, проверяют возможность использования пользователями двух пользователей (litwareinc \\ Pilar и litwareinc \\ kenmyer) для участия в конференции UCWA.</span><span class="sxs-lookup"><span data-stu-id="3a0db-125">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="3a0db-126">Для этого первая команда в примере использует командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="3a0db-126">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="3a0db-127">(Так как имя для входа, litwareinc \\ Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="3a0db-127">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="3a0db-128">Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="3a0db-128">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="3a0db-129">При наличии двух объектов учетных данных в наличии третья команда в примере определяет, могут ли два пользователя участвовать в конференции UCWA.</span><span class="sxs-lookup"><span data-stu-id="3a0db-129">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="3a0db-130">Для запуска этой задачи вызывается командлет **Test-CsUcwaConference** , а также следующие параметры: TargetFqdn (полное доменное имя пула регистратора); Организерсипаддресс (SIP-адрес организатора собрания); Организеркредентиал (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ПартиЦипантсипаддресс (SIP-адрес для другого тестового пользователя); и ПартиЦипанткредентиал (объект интерфейса командной строки Windows PowerShell, который содержит учетные данные для другого пользователя).</span><span class="sxs-lookup"><span data-stu-id="3a0db-130">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3a0db-131">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="3a0db-131">Determining success or failure</span></span>

<span data-ttu-id="3a0db-132">Если Конференц-связь настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="3a0db-132">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3a0db-133">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3a0db-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3a0db-134">Целевой URI: https://Линктест – SE. Линктест. Селфхост. Corp.</span><span class="sxs-lookup"><span data-stu-id="3a0db-134">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="3a0db-135">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="3a0db-135">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="3a0db-136">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="3a0db-136">Result : Success</span></span>

<span data-ttu-id="3a0db-137">Задержка: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="3a0db-137">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="3a0db-138">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="3a0db-138">Error Message :</span></span>

<span data-ttu-id="3a0db-139">Диагност</span><span class="sxs-lookup"><span data-stu-id="3a0db-139">Diagnosis :</span></span>

<span data-ttu-id="3a0db-140">Если указанные пользователи не могут использовать конференц-связь, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="3a0db-140">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3a0db-141">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="3a0db-141">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="3a0db-142">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="3a0db-142">domain name (FQDN).</span></span> <span data-ttu-id="3a0db-143">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3a0db-143">Using default Registrar port number.</span></span> <span data-ttu-id="3a0db-144">Возникновения</span><span class="sxs-lookup"><span data-stu-id="3a0db-144">Exception:</span></span>

<span data-ttu-id="3a0db-145">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="3a0db-145">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="3a0db-146">в</span><span class="sxs-lookup"><span data-stu-id="3a0db-146">at</span></span>

<span data-ttu-id="3a0db-147">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="3a0db-147">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="3a0db-148">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="3a0db-148">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="3a0db-149">Test-CsUcwaConference: нет тестового пользователя, назначенного для</span><span class="sxs-lookup"><span data-stu-id="3a0db-149">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="3a0db-150">\[LyncTest.SelfHost.Corp.Microsoft.com \] .</span><span class="sxs-lookup"><span data-stu-id="3a0db-150">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="3a0db-151">Проверьте конфигурацию тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3a0db-151">Verify test user configuration.</span></span>

<span data-ttu-id="3a0db-152">В строке: 1 символ: 1</span><span class="sxs-lookup"><span data-stu-id="3a0db-152">At line:1 char:1</span></span>

<span data-ttu-id="3a0db-153">\+ Test-CsUcwaConference TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="3a0db-153">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="3a0db-154">\+ Категоринфо: Ресаурцеунаваилабле: (:) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="3a0db-154">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="3a0db-155">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="3a0db-155">, InvalidOperationException</span></span>

<span data-ttu-id="3a0db-156">\+ Фулликуалифиедеррорид: Нотфаундтестусерс, Microsoft. RTC. Management. синтезатор</span><span class="sxs-lookup"><span data-stu-id="3a0db-156">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="3a0db-157">Етиктрансактионс. Тестукваконференцекмдлет</span><span class="sxs-lookup"><span data-stu-id="3a0db-157">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3a0db-158">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="3a0db-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="3a0db-159">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsUcwaConference** :</span><span class="sxs-lookup"><span data-stu-id="3a0db-159">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="3a0db-160">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="3a0db-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3a0db-161">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="3a0db-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3a0db-162">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="3a0db-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3a0db-163">Возможность проведения Конференции зависит от политики конференц-связи, назначенной пользователю, который организует конференцию (в случае командлета **Test-CsUcwaConference** , который является "отправителем").</span><span class="sxs-lookup"><span data-stu-id="3a0db-163">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="3a0db-164">Если организатор не может включать в свое собрание действия для совместной работы (например, если для свойства Енабледатаколлаборатион в политике конференц-связи задано значение false), командлет **Test-CsUcwaConference** завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="3a0db-164">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="3a0db-165">Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="3a0db-165">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a0db-166">См. также</span><span class="sxs-lookup"><span data-stu-id="3a0db-166">See Also</span></span>


[<span data-ttu-id="3a0db-167">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="3a0db-167">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="3a0db-168">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="3a0db-168">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="3a0db-169">Test-Ксавконференце</span><span class="sxs-lookup"><span data-stu-id="3a0db-169">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

