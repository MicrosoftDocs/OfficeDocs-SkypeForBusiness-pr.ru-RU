---
title: 'Lync Server 2013: тестирование возможности группового обмена мгновенными сообщениями'
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
ms.openlocfilehash: eef76c8728a7b5a569efee9305505f4e19f6bceb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="2ae7c-102">Тестирование возможности группового обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae7c-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ae7c-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2ae7c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ae7c-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="2ae7c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2ae7c-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="2ae7c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae7c-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="2ae7c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2ae7c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ae7c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae7c-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="2ae7c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2ae7c-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2ae7c-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="2ae7c-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2ae7c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2ae7c-112">Description</span></span>

<span data-ttu-id="2ae7c-113">Командлет Test-CsGroupIM проверяет, могут ли пользователи в вашей организации выполнять сеансы группы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="2ae7c-114">При выполнении командлета Test-CsGroupIM командлет пытается войти в систему на сервере Lync Server в сочетании тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="2ae7c-115">При успешном входе Test-CsGroupIM создает конференцию с помощью первого тестового пользователя, а затем приглашает второго пользователя присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="2ae7c-116">После обмена сообщениями оба пользователя отключаются от системы.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="2ae7c-117">Обратите внимание, что все это происходит без участия пользователя и не влияет на реальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="2ae7c-118">Например, предположим, что тестовая учетная запись sip:kenmyer@litwareinc.com соответствует реальному пользователю с действительной учетной записью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="2ae7c-119">В этом случае тест будет проведен без прерывания работы пользователя Кен Майер (Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="2ae7c-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="2ae7c-120">Например, даже если тестовая учетная запись Кена Майера выходит из системы, сам Кен Майер останется в системе.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="2ae7c-121">Аналогично, настоящие Myer не получат приглашение присоединиться к Конференции.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="2ae7c-122">Оно будет отправлено и принято тестовой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="2ae7c-123">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="2ae7c-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2ae7c-124">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="2ae7c-124">Running the test</span></span>

<span data-ttu-id="2ae7c-125">Командлет Test-CsGroupIM можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетных записей двух пользователей с включенной поддержкой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="2ae7c-126">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="2ae7c-127">Например:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="2ae7c-128">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных командной консоли Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="2ae7c-129">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsGroupIM:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="2ae7c-130">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="2ae7c-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2ae7c-131">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="2ae7c-131">Determining Success or Failure</span></span>

<span data-ttu-id="2ae7c-132">Если два пользователя могут выполнить сеанс обмена мгновенными сообщениями, будет выведен результат, подобный следующему, с помощью свойства Result, помеченного как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="2ae7c-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2ae7c-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2ae7c-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2ae7c-134">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="2ae7c-134">Result : Success</span></span>

<span data-ttu-id="2ae7c-135">Задержка: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="2ae7c-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="2ae7c-136">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="2ae7c-136">Error :</span></span>

<span data-ttu-id="2ae7c-137">Диагност</span><span class="sxs-lookup"><span data-stu-id="2ae7c-137">Diagnosis :</span></span>

<span data-ttu-id="2ae7c-138">Если двум пользователям не удается завершить сеанс обмена мгновенными сообщениями, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2ae7c-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2ae7c-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2ae7c-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="2ae7c-140">Result : Failure</span></span>

<span data-ttu-id="2ae7c-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="2ae7c-141">Latency : 00:00:00</span></span>

<span data-ttu-id="2ae7c-142">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="2ae7c-142">Error : 404, Not Found</span></span>

<span data-ttu-id="2ae7c-143">Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="2ae7c-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="2ae7c-144">Reason = конечный URI либо не включен для SIP, либо не</span><span class="sxs-lookup"><span data-stu-id="2ae7c-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="2ae7c-145">есть.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-145">exist.</span></span>

<span data-ttu-id="2ae7c-146">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="2ae7c-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="2ae7c-147">Предыдущие выходные данные появлялись, что не удалось выполнить тест, так как по крайней мере одна из тестовых учетных записей была недействительной, так как учетная запись не существует или у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="2ae7c-148">Вы можете проверить существование учетной записи, а также указать, включена ли учетная запись для NM-OCS-14-3, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="2ae7c-149">Если Test-CsGroupIM завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="2ae7c-150">Если включен параметр Verbose, Test-CsGroupIM будет возвращать пошаговые учетные записи каждого выполняемого действия, когда он проверил возможность участия указанных пользователей в сеансах группы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="2ae7c-151">Например, если тест завершается с ошибкой, и вы сообщаете, что одна или несколько учетных записей пользователей являются недопустимыми, вы можете повторно выполнить тест с параметром verbose и определить, какая учетная запись пользователя является недопустимой:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="2ae7c-152">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-152">Sending Registration request:</span></span>

 <span data-ttu-id="2ae7c-153">Целевое полное доменное имя = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2ae7c-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="2ae7c-154">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2ae7c-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="2ae7c-155">Зарегистрировать порт = 5061</span><span class="sxs-lookup"><span data-stu-id="2ae7c-155">Register Port    = 5061</span></span>

<span data-ttu-id="2ae7c-156">Выбран тип проверки подлинности "Ива".</span><span class="sxs-lookup"><span data-stu-id="2ae7c-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="2ae7c-157">Исключение "при входе в систему было отклонено.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="2ae7c-158">Убедитесь, что используются правильные учетные данные, а учетная запись активна.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="2ae7c-159">Как вы видите, в этом примере пользователь, у которого есть SIP Address sip:kenmyer@litwareinc.com, не смог выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2ae7c-160">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="2ae7c-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="2ae7c-161">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsGroupIM:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="2ae7c-162">Вы указали неправильную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-162">You specified an incorrect user account.</span></span> <span data-ttu-id="2ae7c-163">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2ae7c-164">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2ae7c-165">Чтобы убедиться, что учетная запись пользователя была включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="2ae7c-166">Get – CsUser "sip:kenmyer@litwareinc.com" | Select – объект включен</span><span class="sxs-lookup"><span data-stu-id="2ae7c-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="2ae7c-167">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="2ae7c-168">Служба обмена мгновенными сообщениями может быть недоступна.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="2ae7c-169">С помощью Lync Server можно настроить систему таким образом, чтобы мгновенные сообщения не были доступны, если не удается получить доступ к базе данных архивации.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="2ae7c-170">Это можно проверить, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="2ae7c-171">Если для Блокконарчивефаилуре задано значение true, то следует определить, доступна ли база данных архивации.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="2ae7c-172">Вы можете вернуть расположения баз данных архивации с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="2ae7c-173">Сервер архивации может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="2ae7c-174">С помощью этой команды можно получить полное доменное имя серверов архивации:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="2ae7c-175">После этого вы можете проверить связь с соответствующим сервером, чтобы убедиться, что он доступен.</span><span class="sxs-lookup"><span data-stu-id="2ae7c-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="2ae7c-176">Пример:</span><span class="sxs-lookup"><span data-stu-id="2ae7c-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

