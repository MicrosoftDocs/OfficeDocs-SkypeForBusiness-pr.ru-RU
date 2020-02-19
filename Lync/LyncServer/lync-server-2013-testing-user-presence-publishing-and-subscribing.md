---
title: 'Lync Server 2013: тестирование публикации и подписки на присутствие пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76cd47ccfe35cecf7b7e9182aeadccc37436bc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="8dd08-102">Тестирование публикации и подписки на присутствие пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dd08-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dd08-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8dd08-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dd08-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="8dd08-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8dd08-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="8dd08-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd08-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="8dd08-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8dd08-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dd08-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dd08-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="8dd08-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8dd08-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8dd08-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8dd08-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsPresence.</span><span class="sxs-lookup"><span data-stu-id="8dd08-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="8dd08-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8dd08-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8dd08-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8dd08-112">Description</span></span>

<span data-ttu-id="8dd08-113">Test-CsPresence используется для определения того, может ли пользователь, который является членом теста, войти в Lync Server, а затем сведения о присутствии Exchange.</span><span class="sxs-lookup"><span data-stu-id="8dd08-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="8dd08-114">Сначала командлет выполняет вход в систему от имени этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="8dd08-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="8dd08-115">Если удается выполнить оба входа, первый тестовый пользователь запрашивает сведения о присутствии у второго пользователя.</span><span class="sxs-lookup"><span data-stu-id="8dd08-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="8dd08-116">Второй пользователь публикует эти сведения, а командлет Test-CsPresence проверяет, что они успешно переданы первому пользователю.</span><span class="sxs-lookup"><span data-stu-id="8dd08-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="8dd08-117">После обмена сведениями о присутствии два тестовых пользователя после выхода из Lync Server выводятся из Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dd08-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8dd08-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="8dd08-118">Running the test</span></span>

<span data-ttu-id="8dd08-119">Командлет Test-CsPresence можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетных записей двух пользователей с включенной поддержкой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dd08-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="8dd08-120">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dd08-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="8dd08-121">Например:</span><span class="sxs-lookup"><span data-stu-id="8dd08-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="8dd08-122">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="8dd08-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="8dd08-123">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsPresence:</span><span class="sxs-lookup"><span data-stu-id="8dd08-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="8dd08-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="8dd08-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8dd08-125">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="8dd08-125">Determining success or failure</span></span>

<span data-ttu-id="8dd08-126">Если указанные пользователи могут обмениваться сведениями о присутствии, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success.**</span><span class="sxs-lookup"><span data-stu-id="8dd08-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="8dd08-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8dd08-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8dd08-128">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="8dd08-128">Result : Success</span></span>

<span data-ttu-id="8dd08-129">Задержка: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="8dd08-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="8dd08-130">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="8dd08-130">Error :</span></span>

<span data-ttu-id="8dd08-131">Диагност</span><span class="sxs-lookup"><span data-stu-id="8dd08-131">Diagnosis :</span></span>

<span data-ttu-id="8dd08-132">Если два пользователя не могут обмениваться сведениями о присутствии, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="8dd08-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8dd08-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8dd08-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8dd08-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="8dd08-134">Result : Failure</span></span>

<span data-ttu-id="8dd08-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8dd08-135">Latency : 00:00:00</span></span>

<span data-ttu-id="8dd08-136">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="8dd08-136">Error : 404, Not Found</span></span>

<span data-ttu-id="8dd08-137">Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="8dd08-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="8dd08-138">Reason = конечный URI либо не включен для SIP, либо не</span><span class="sxs-lookup"><span data-stu-id="8dd08-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="8dd08-139">есть.</span><span class="sxs-lookup"><span data-stu-id="8dd08-139">exist.</span></span>

<span data-ttu-id="8dd08-140">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="8dd08-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="8dd08-141">Например, предыдущее выходное состояние не удалось выполнить тест, так как по крайней мере одна из двух учетных записей пользователей является недопустимой: либо учетная запись не существует, либо она не была включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dd08-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="8dd08-142">Вы можете убедиться, что учетные записи существуют, и определить, включены ли они для Lync Server, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8dd08-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="8dd08-143">Если Test-CsPresence завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="8dd08-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="8dd08-144">Если включен параметр Verbose, командлет Test-CsPresence возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dd08-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="8dd08-145">Например:</span><span class="sxs-lookup"><span data-stu-id="8dd08-145">For example:</span></span>

<span data-ttu-id="8dd08-146">Попадание в запрос на регистрацию для неизвестного</span><span class="sxs-lookup"><span data-stu-id="8dd08-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="8dd08-147">Действие ' Register ' завершено в ' 0,0345791 ' сек.</span><span class="sxs-lookup"><span data-stu-id="8dd08-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="8dd08-148">Начато действие "Селфсубскрибеактивити".</span><span class="sxs-lookup"><span data-stu-id="8dd08-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="8dd08-149">Действие ' Селфсубскрибеактивити ' завершено в ' 0,0041174 ' сек.</span><span class="sxs-lookup"><span data-stu-id="8dd08-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="8dd08-150">Начато действие "Субскрибепресенце".</span><span class="sxs-lookup"><span data-stu-id="8dd08-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="8dd08-151">Действие ' Субскрибепресенце ' завершено в ' 0,0038764 ' сек.</span><span class="sxs-lookup"><span data-stu-id="8dd08-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="8dd08-152">Начато действие "Публишпресенце".</span><span class="sxs-lookup"><span data-stu-id="8dd08-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="8dd08-153">Уведомление о присутствии не получается в течение 25 сек.</span><span class="sxs-lookup"><span data-stu-id="8dd08-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="8dd08-154">произошла ошибка руинг рабочего процесса Microsoft. RTC. SyntheticTransactions. Workflows. Стпресенцеворкфлов Execution.</span><span class="sxs-lookup"><span data-stu-id="8dd08-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="8dd08-155">Тот факт, что уведомление о присутствии не было получено в течение 25 секунд, может означать, что проблемы с сетью препятствуют обмену данными.</span><span class="sxs-lookup"><span data-stu-id="8dd08-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8dd08-156">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="8dd08-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="8dd08-157">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsPresence:</span><span class="sxs-lookup"><span data-stu-id="8dd08-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="8dd08-158">Вы указали неправильную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="8dd08-158">You specified an incorrect user account.</span></span> <span data-ttu-id="8dd08-159">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8dd08-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="8dd08-160">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dd08-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="8dd08-161">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="8dd08-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="8dd08-162">Если для свойства Enabled задано значение false, то в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dd08-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

