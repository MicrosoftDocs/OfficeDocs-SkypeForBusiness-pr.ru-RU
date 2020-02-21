---
title: 'Lync Server 2013: тестирование конференц-связи по UCWA'
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
ms.openlocfilehash: af4bd6dd911b43714dffa48c3b21d3329b2aaa01
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="4b54f-102">Тестирование конференц-связи UCWA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b54f-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b54f-103">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="4b54f-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b54f-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="4b54f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4b54f-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="4b54f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b54f-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="4b54f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4b54f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b54f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b54f-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="4b54f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4b54f-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4b54f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4b54f-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsUcwaConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="4b54f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="4b54f-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4b54f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4b54f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4b54f-112">Description</span></span>

<span data-ttu-id="4b54f-113">Командлет **Test-CsUcwaConference** проверяет, может ли пользователь, запланировать, присоединиться к Конференции, а затем провести интерактивную конференцию с помощью веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="4b54f-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="4b54f-114">Для этого командлет использует службу веб-билета Lync Server для проверки подлинности двух тестовых пользователей и их регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b54f-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="4b54f-115">Командлет затем запускает конференцию с помощью учетных данных организатора и приглашает участника присоединиться к встрече.</span><span class="sxs-lookup"><span data-stu-id="4b54f-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="4b54f-116">После подключения к собранию командлет **Test-CsUcwaConference** проверяет, могут ли пользователи выполнять такие действия, как обмен мгновенными сообщениями и проведение пулов, а затем отключает конференцию и отменяет регистрацию двух тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b54f-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="4b54f-117">Запланированная Конференция также будет удалена после завершения теста.</span><span class="sxs-lookup"><span data-stu-id="4b54f-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="4b54f-118">Командлет **Test-CsUcwaConference** также можно использовать, чтобы определить, могут ли анонимные пользователи присоединяться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="4b54f-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="4b54f-119">Обратите внимание на то, что командлет **Test-CsUcwaConference** не следует запускать для пула Microsoft Lync Server 2010, если UCWA не установлен в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="4b54f-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="4b54f-120">Если UCWA не установлен, вызов командлета **Test-CsUcwaConference** завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="4b54f-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4b54f-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="4b54f-121">Running the test</span></span>

<span data-ttu-id="4b54f-p104">Команда, показанная в Примере 1 проверяет возможность для пары тестовых пользователей принимать участие в конференции UCWA на пуле atl-cs-001.litwareinc.com. Обратите внимание, что эта команда не будет выполнена успешно, если заранее не определены тестовые пользователи конфигурации мониторинга состояния для atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4b54f-p104">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="4b54f-124">Команды, показанные в примере 2, проверяют возможность использования пользователями двух пользователей (\\litwareinc Pilar и\\litwareinc kenmyer) для участия в конференции UCWA.</span><span class="sxs-lookup"><span data-stu-id="4b54f-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="4b54f-125">Для этого первая команда в примере использует командлет Get – Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="4b54f-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="4b54f-126">(Так как имя для входа,\\litwareinc Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="4b54f-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="4b54f-127">Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4b54f-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="4b54f-128">При наличии двух объектов учетных данных в наличии третья команда в примере определяет, могут ли два пользователя участвовать в конференции UCWA.</span><span class="sxs-lookup"><span data-stu-id="4b54f-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="4b54f-129">Для запуска этой задачи вызывается командлет **Test-CsUcwaConference** , а также следующие параметры: TargetFqdn (полное доменное имя пула регистратора); Организерсипаддресс (SIP-адрес организатора собрания); Организеркредентиал (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ПартиЦипантсипаддресс (SIP-адрес для другого тестового пользователя); и ПартиЦипанткредентиал (объект интерфейса командной строки Windows PowerShell, который содержит учетные данные для другого пользователя).</span><span class="sxs-lookup"><span data-stu-id="4b54f-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4b54f-130">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="4b54f-130">Determining success or failure</span></span>

<span data-ttu-id="4b54f-131">Если Конференц-связь настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="4b54f-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="4b54f-132">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b54f-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4b54f-133">Целевой URI: https://Линктест – SE. Линктест. Селфхост. Corp.</span><span class="sxs-lookup"><span data-stu-id="4b54f-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="4b54f-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="4b54f-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="4b54f-135">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="4b54f-135">Result : Success</span></span>

<span data-ttu-id="4b54f-136">Задержка: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="4b54f-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="4b54f-137">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="4b54f-137">Error Message :</span></span>

<span data-ttu-id="4b54f-138">Диагност</span><span class="sxs-lookup"><span data-stu-id="4b54f-138">Diagnosis :</span></span>

<span data-ttu-id="4b54f-139">Если указанные пользователи не могут использовать конференц-связь, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="4b54f-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4b54f-140">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="4b54f-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="4b54f-141">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="4b54f-141">domain name (FQDN).</span></span> <span data-ttu-id="4b54f-142">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b54f-142">Using default Registrar port number.</span></span> <span data-ttu-id="4b54f-143">Возникновения</span><span class="sxs-lookup"><span data-stu-id="4b54f-143">Exception:</span></span>

<span data-ttu-id="4b54f-144">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="4b54f-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="4b54f-145">в</span><span class="sxs-lookup"><span data-stu-id="4b54f-145">at</span></span>

<span data-ttu-id="4b54f-146">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="4b54f-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="4b54f-147">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="4b54f-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="4b54f-148">Test-CsUcwaConference: нет тестового пользователя, назначенного для</span><span class="sxs-lookup"><span data-stu-id="4b54f-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="4b54f-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="4b54f-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="4b54f-150">Проверьте конфигурацию тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b54f-150">Verify test user configuration.</span></span>

<span data-ttu-id="4b54f-151">В строке: 1 символ: 1</span><span class="sxs-lookup"><span data-stu-id="4b54f-151">At line:1 char:1</span></span>

<span data-ttu-id="4b54f-152">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="4b54f-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="4b54f-153">\+Категоринфо: Ресаурцеунаваилабле: (:) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="4b54f-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="4b54f-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="4b54f-154">, InvalidOperationException</span></span>

<span data-ttu-id="4b54f-155">\+Фулликуалифиедеррорид: Нотфаундтестусерс, Microsoft. RTC. Management. синтезатор</span><span class="sxs-lookup"><span data-stu-id="4b54f-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="4b54f-156">Етиктрансактионс. Тестукваконференцекмдлет</span><span class="sxs-lookup"><span data-stu-id="4b54f-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4b54f-157">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="4b54f-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="4b54f-158">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsUcwaConference** :</span><span class="sxs-lookup"><span data-stu-id="4b54f-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="4b54f-159">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="4b54f-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="4b54f-160">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="4b54f-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="4b54f-161">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="4b54f-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="4b54f-162">Возможность проведения Конференции зависит от политики конференц-связи, назначенной пользователю, который организует конференцию (в случае командлета **Test-CsUcwaConference** , который является "отправителем").</span><span class="sxs-lookup"><span data-stu-id="4b54f-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="4b54f-163">Если организатор не может включать в свое собрание действия для совместной работы (например, если для свойства Енабледатаколлаборатион в политике конференц-связи задано значение false), командлет **Test-CsUcwaConference** завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="4b54f-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="4b54f-164">Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="4b54f-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b54f-165">См. также</span><span class="sxs-lookup"><span data-stu-id="4b54f-165">See Also</span></span>


[<span data-ttu-id="4b54f-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="4b54f-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="4b54f-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="4b54f-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="4b54f-168">Test-Ксавконференце</span><span class="sxs-lookup"><span data-stu-id="4b54f-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

