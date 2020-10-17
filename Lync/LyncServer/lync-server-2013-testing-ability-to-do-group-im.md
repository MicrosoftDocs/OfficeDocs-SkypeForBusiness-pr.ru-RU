---
title: 'Lync Server 2013: тестирование возможности группового обмена мгновенными сообщениями'
description: 'Lync Server 2013: тестирование возможности группового обмена мгновенными сообщениями.'
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
ms.openlocfilehash: f6988a0c1a7ba569f7b4da098ae741beab5e14fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560815"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="cc0b7-103">Тестирование возможности группового обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc0b7-103">Testing ability to do group IM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc0b7-104">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="cc0b7-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc0b7-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="cc0b7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cc0b7-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="cc0b7-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc0b7-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="cc0b7-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cc0b7-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc0b7-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc0b7-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="cc0b7-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cc0b7-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cc0b7-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="cc0b7-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cc0b7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cc0b7-113">Description</span></span>

<span data-ttu-id="cc0b7-114">Командлет Test-CsGroupIM проверяет, могут ли пользователи в вашей организации выполнять сеансы группы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-114">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="cc0b7-115">При выполнении командлета Test-CsGroupIM командлет пытается войти в систему на сервере Lync Server в сочетании тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-115">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="cc0b7-116">При успешном входе Test-CsGroupIM создает конференцию с помощью первого тестового пользователя, а затем приглашает второго пользователя присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-116">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="cc0b7-117">После обмена сообщениями оба пользователя отключаются от системы.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-117">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="cc0b7-118">Обратите внимание, что все это происходит без участия пользователя и не влияет на реальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-118">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="cc0b7-119">Например, предположим, что тестовая учетная запись sip:kenmyer@litwareinc.com соответствует реальному пользователю с действительной учетной записью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-119">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="cc0b7-120">В этом случае тест будет проведен без прерывания работы пользователя Кен Майер (Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="cc0b7-120">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="cc0b7-121">Например, даже если тестовая учетная запись Кена Майера выходит из системы, сам Кен Майер останется в системе.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-121">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="cc0b7-122">Аналогично, настоящие Myer не получат приглашение присоединиться к Конференции.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-122">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="cc0b7-123">Оно будет отправлено и принято тестовой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-123">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="cc0b7-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="cc0b7-124">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cc0b7-125">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="cc0b7-125">Running the test</span></span>

<span data-ttu-id="cc0b7-126">Командлет Test-CsGroupIM можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для запуска тестов Lync Server) или учетных записей двух пользователей, для которых включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-126">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="cc0b7-127">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-127">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="cc0b7-128">Например:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-128">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="cc0b7-129">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных командной консоли Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-129">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="cc0b7-130">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsGroupIM:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-130">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="cc0b7-131">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="cc0b7-131">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cc0b7-132">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="cc0b7-132">Determining Success or Failure</span></span>

<span data-ttu-id="cc0b7-133">Если два пользователя могут выполнить сеанс обмена мгновенными сообщениями, будет выведен результат, подобный следующему, с помощью свойства Result, помеченного как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="cc0b7-133">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="cc0b7-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc0b7-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cc0b7-135">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="cc0b7-135">Result : Success</span></span>

<span data-ttu-id="cc0b7-136">Задержка: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="cc0b7-136">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="cc0b7-137">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="cc0b7-137">Error :</span></span>

<span data-ttu-id="cc0b7-138">Диагност</span><span class="sxs-lookup"><span data-stu-id="cc0b7-138">Diagnosis :</span></span>

<span data-ttu-id="cc0b7-139">Если двум пользователям не удается завершить сеанс обмена мгновенными сообщениями, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-139">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="cc0b7-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc0b7-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cc0b7-141">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="cc0b7-141">Result : Failure</span></span>

<span data-ttu-id="cc0b7-142">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="cc0b7-142">Latency : 00:00:00</span></span>

<span data-ttu-id="cc0b7-143">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="cc0b7-143">Error : 404, Not Found</span></span>

<span data-ttu-id="cc0b7-144">Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="cc0b7-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="cc0b7-145">Reason = конечный URI либо не включен для SIP, либо не</span><span class="sxs-lookup"><span data-stu-id="cc0b7-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="cc0b7-146">есть.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-146">exist.</span></span>

<span data-ttu-id="cc0b7-147">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="cc0b7-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="cc0b7-148">Предыдущие выходные данные появлялись, что не удалось выполнить тест, так как по крайней мере одна из тестовых учетных записей была недействительной, так как учетная запись не существует или у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-148">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="cc0b7-149">Вы можете проверить существование учетной записи, а также указать, включена ли учетная запись для NM-OCS-14-3, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-149">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="cc0b7-150">Если Test-CsGroupIM завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-150">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="cc0b7-151">Если включен параметр Verbose, Test-CsGroupIM будет возвращать пошаговые учетные записи для каждого выполняемого действия, когда он проверил возможность участия указанных пользователей в сеансах группы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-151">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="cc0b7-152">Например, если тест завершается с ошибкой, и вы сообщаете, что одна или несколько учетных записей пользователей являются недопустимыми, вы можете повторно выполнить тест с параметром verbose и определить, какая учетная запись пользователя является недопустимой:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-152">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="cc0b7-153">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-153">Sending Registration request:</span></span>

 <span data-ttu-id="cc0b7-154">Целевое полное доменное имя = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc0b7-154">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="cc0b7-155">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc0b7-155">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="cc0b7-156">Зарегистрировать порт = 5061</span><span class="sxs-lookup"><span data-stu-id="cc0b7-156">Register Port    = 5061</span></span>

<span data-ttu-id="cc0b7-157">Выбран тип проверки подлинности "Ива".</span><span class="sxs-lookup"><span data-stu-id="cc0b7-157">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="cc0b7-158">Исключение "при входе в систему было отклонено.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-158">An exception 'The log on was denied.</span></span> <span data-ttu-id="cc0b7-159">Убедитесь, что используются правильные учетные данные, а учетная запись активна.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-159">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="cc0b7-160">Как вы видите, в этом примере пользователь, у которого есть SIP Address sip:kenmyer@litwareinc.com, не смог выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-160">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cc0b7-161">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="cc0b7-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="cc0b7-162">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsGroupIM:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-162">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="cc0b7-163">Вы указали неправильную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-163">You specified an incorrect user account.</span></span> <span data-ttu-id="cc0b7-164">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="cc0b7-165">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-165">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="cc0b7-166">Чтобы убедиться, что учетная запись пользователя была включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-166">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="cc0b7-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object включена</span><span class="sxs-lookup"><span data-stu-id="cc0b7-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="cc0b7-168">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="cc0b7-169">Служба обмена мгновенными сообщениями может быть недоступна.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-169">The instant messaging service might not be available.</span></span> <span data-ttu-id="cc0b7-170">С помощью Lync Server можно настроить систему таким образом, чтобы мгновенные сообщения не были доступны, если не удается получить доступ к базе данных архивации.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-170">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="cc0b7-171">Это можно проверить, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-171">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="cc0b7-172">Если для Блокконарчивефаилуре задано значение true, то следует определить, доступна ли база данных архивации.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-172">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="cc0b7-173">Вы можете вернуть расположения баз данных архивации с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-173">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="cc0b7-174">Сервер архивации может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-174">The Archiving Server might not be available.</span></span> <span data-ttu-id="cc0b7-175">С помощью этой команды можно получить полное доменное имя серверов архивации:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-175">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="cc0b7-176">После этого вы можете проверить связь с соответствующим сервером, чтобы убедиться, что он доступен.</span><span class="sxs-lookup"><span data-stu-id="cc0b7-176">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="cc0b7-177">Пример:</span><span class="sxs-lookup"><span data-stu-id="cc0b7-177">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

