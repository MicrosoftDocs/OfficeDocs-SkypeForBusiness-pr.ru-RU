---
title: 'Lync Server 2013: Проверка возможности группового обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="3d540-102">Тестирование возможности группового обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d540-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d540-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3d540-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d540-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="3d540-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3d540-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="3d540-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d540-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="3d540-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3d540-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d540-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d540-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="3d540-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3d540-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="3d540-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3d540-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксграупим.</span><span class="sxs-lookup"><span data-stu-id="3d540-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="3d540-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d540-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3d540-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3d540-112">Description</span></span>

<span data-ttu-id="3d540-113">Командлет Test-Ксграупим удостоверяется в том, что пользователи в вашей организации могут проводить групповые сеансы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="3d540-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="3d540-114">При запуске test-Ксграупим командлет пытается войти в систему на сервере Lync Server в паре тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="3d540-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="3d540-115">При успешном выполнении команды Test-Ксграупим создает новую конференцию с помощью первого тестового пользователя, а затем приглашает второго пользователя присоединиться к Конференции.</span><span class="sxs-lookup"><span data-stu-id="3d540-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="3d540-116">После обмена сообщениями оба пользователя отключаются от системы.</span><span class="sxs-lookup"><span data-stu-id="3d540-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="3d540-117">Обратите внимание, что все это происходит без взаимодействия с пользователем и без воздействия каких – либо реальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3d540-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="3d540-118">Например, предположим, что проверка учетной записи sip:kenmyer@litwareinc.comа с реальным пользователем, у которого есть учетная запись сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d540-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="3d540-119">В этом случае тест будет проводиться без перерывов в работе Кен мер.</span><span class="sxs-lookup"><span data-stu-id="3d540-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="3d540-120">Например, даже когда Кен мер тестовая учетная запись выходит из системы, Кен мер человека останется на входе.</span><span class="sxs-lookup"><span data-stu-id="3d540-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="3d540-121">Кроме того, мер Кен не получит приглашение присоединиться к Конференции.</span><span class="sxs-lookup"><span data-stu-id="3d540-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="3d540-122">Это приглашение будет отправлено и принято для тестового счета.</span><span class="sxs-lookup"><span data-stu-id="3d540-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="3d540-123">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупим](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="3d540-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3d540-124">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="3d540-124">Running the test</span></span>

<span data-ttu-id="3d540-125">Командлет Test-Ксграупим можно выполнить с помощью пары предварительно настроенных тестовых учетных записей (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетные записи любых двух пользователей, которые включены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d540-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="3d540-126">Для выполнения этой проверки с помощью тестовых учетных записей нужно просто указать полное доменное имя для тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d540-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="3d540-127">Например:</span><span class="sxs-lookup"><span data-stu-id="3d540-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3d540-128">Для выполнения этой проверки с использованием фактических учетных записей пользователей необходимо создать два объекта учетных данных командной консоли Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3d540-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="3d540-129">После вызова Test-Ксграупим вы должны добавить эти объекты учетных данных и адреса SIP для двух учетных записей.</span><span class="sxs-lookup"><span data-stu-id="3d540-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="3d540-130">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупим](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="3d540-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3d540-131">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="3d540-131">Determining Success or Failure</span></span>

<span data-ttu-id="3d540-132">Если два пользователя могут завершить сеанс обмена мгновенными сообщениями, вы получите вывод примерно так, чтобы свойство Result пометило **"успешно".**</span><span class="sxs-lookup"><span data-stu-id="3d540-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3d540-133">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d540-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d540-134">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="3d540-134">Result : Success</span></span>

<span data-ttu-id="3d540-135">Задержка: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="3d540-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="3d540-136">Ошибки</span><span class="sxs-lookup"><span data-stu-id="3d540-136">Error :</span></span>

<span data-ttu-id="3d540-137">Диагностик</span><span class="sxs-lookup"><span data-stu-id="3d540-137">Diagnosis :</span></span>

<span data-ttu-id="3d540-138">Если два пользователя не могут завершить сеанс обмена мгновенными сообщениями, результат будет показан в виде ошибки, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="3d540-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3d540-139">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d540-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d540-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="3d540-140">Result : Failure</span></span>

<span data-ttu-id="3d540-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3d540-141">Latency : 00:00:00</span></span>

<span data-ttu-id="3d540-142">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="3d540-142">Error : 404, Not Found</span></span>

<span data-ttu-id="3d540-143">Диагностика: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="3d540-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="3d540-144">Reason = универсальный код ресурса (URI) назначения не включен для SIP либо не</span><span class="sxs-lookup"><span data-stu-id="3d540-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="3d540-145">Существует.</span><span class="sxs-lookup"><span data-stu-id="3d540-145">exist.</span></span>

<span data-ttu-id="3d540-146">Microsoft. RTC. SignalR. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="3d540-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="3d540-147">В предыдущем выводе говорится, что тест завершился сбоем, так как по крайней мере одна из тестовых учетных записей была недействительной из-за отсутствия учетной записи или из-за того, что пользователь не включен в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d540-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="3d540-148">Вы можете проверить существование учетной записи, а также включить или отключить ее для NM-OCS-14-3, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d540-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="3d540-149">Если при выполнении теста-Ксграупим происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="3d540-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="3d540-150">При включенном параметре "подробный" функция Test-Ксграупим будет возвращать пошаговые учетные записи для каждого действия, которое он пытался принять, когда вы проверили возможность участия указанных пользователей в сеансах группового обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="3d540-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="3d540-151">Например, если при выполнении теста возникла ошибка, и вы сообщаете, что одна или несколько учетных записей пользователей не являются допустимыми, вы можете повторно запустить тест с помощью параметра подробный и определить, какая учетная запись пользователя недействительна.</span><span class="sxs-lookup"><span data-stu-id="3d540-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="3d540-152">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="3d540-152">Sending Registration request:</span></span>

 <span data-ttu-id="3d540-153">Целевое полное доменное имя = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d540-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="3d540-154">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d540-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="3d540-155">Зарегистрировать порт = 5061</span><span class="sxs-lookup"><span data-stu-id="3d540-155">Register Port    = 5061</span></span>

<span data-ttu-id="3d540-156">Выбран тип проверки подлинности "Ива".</span><span class="sxs-lookup"><span data-stu-id="3d540-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="3d540-157">Исключение "вход был отклонен".</span><span class="sxs-lookup"><span data-stu-id="3d540-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="3d540-158">Убедитесь в том, что используются правильные учетные данные, а учетная запись активна.</span><span class="sxs-lookup"><span data-stu-id="3d540-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="3d540-159">Как видите, в этом примере пользователь, которому предоставлен адрес SIP sip:kenmyer@litwareinc.com, не смог войти в систему.</span><span class="sxs-lookup"><span data-stu-id="3d540-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3d540-160">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="3d540-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="3d540-161">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксграупим:</span><span class="sxs-lookup"><span data-stu-id="3d540-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="3d540-162">Вы указали неверную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d540-162">You specified an incorrect user account.</span></span> <span data-ttu-id="3d540-163">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d540-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3d540-164">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d540-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="3d540-165">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="3d540-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="3d540-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Выбор-объект включен</span><span class="sxs-lookup"><span data-stu-id="3d540-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="3d540-167">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d540-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="3d540-168">Возможно, служба мгновенных сообщений недоступна.</span><span class="sxs-lookup"><span data-stu-id="3d540-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="3d540-169">С помощью Lync Server вы можете настроить систему таким образом, чтобы мгновенные сообщения не были доступны, если не удается получить доступ к базе данных архивации.</span><span class="sxs-lookup"><span data-stu-id="3d540-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="3d540-170">Это можно проверить, выполнив команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="3d540-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="3d540-171">Если для Блокконарчивефаилуре задано значение "true", необходимо определить, доступна ли база данных архивации.</span><span class="sxs-lookup"><span data-stu-id="3d540-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="3d540-172">Вы можете вернуть расположение баз данных архивации с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="3d540-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="3d540-173">Сервер архивации может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="3d540-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="3d540-174">Вы можете получить полное доменное имя серверов архивации с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="3d540-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="3d540-175">Затем вы можете обратиться к соответствующему серверу, чтобы убедиться, что он доступен.</span><span class="sxs-lookup"><span data-stu-id="3d540-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="3d540-176">Например:</span><span class="sxs-lookup"><span data-stu-id="3d540-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

