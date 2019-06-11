---
title: 'Lync Server 2013: Проверка публикации и подписки на присутствие пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7052550067868ff201c809a51e1d119c5f8a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="67a67-102">Проверка публикации и подписки на присутствие пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67a67-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67a67-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="67a67-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67a67-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="67a67-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="67a67-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="67a67-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67a67-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="67a67-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="67a67-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67a67-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67a67-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="67a67-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="67a67-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="67a67-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="67a67-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кспресенце.</span><span class="sxs-lookup"><span data-stu-id="67a67-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="67a67-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="67a67-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="67a67-112">Описание</span><span class="sxs-lookup"><span data-stu-id="67a67-112">Description</span></span>

<span data-ttu-id="67a67-113">Test-Кспресенце используется, чтобы определить, может ли пользовательская учетная запись входить на сервер Lync Server, а затем обмениваться сведениями о присутствии.</span><span class="sxs-lookup"><span data-stu-id="67a67-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="67a67-114">Для этого командлет сначала заносит в нее двух пользователей в систему.</span><span class="sxs-lookup"><span data-stu-id="67a67-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="67a67-115">Если оба входа выполняются успешно, первый тестовый пользователь запрашивает получение сведений о присутствии от второго пользователя.</span><span class="sxs-lookup"><span data-stu-id="67a67-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="67a67-116">Второй пользователь публикует эти данные, а Test-Кспресенце подтверждает, что данные были успешно переданы первому пользователю.</span><span class="sxs-lookup"><span data-stu-id="67a67-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="67a67-117">После получения сведений о присутствии два тестовых пользователя затем выключаются из Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a67-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="67a67-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="67a67-118">Running the test</span></span>

<span data-ttu-id="67a67-119">Командлет Test-Кспресенце можно выполнить с помощью пары предварительно настроенных тестовых учетных записей (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетные записи любых двух пользователей, которые включены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a67-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="67a67-120">Для выполнения этой проверки с помощью тестовых учетных записей нужно просто указать полное доменное имя для тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a67-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="67a67-121">Например:</span><span class="sxs-lookup"><span data-stu-id="67a67-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="67a67-122">Для выполнения этой проверки с использованием фактических учетных записей пользователей необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="67a67-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="67a67-123">После вызова Test-Кспресенце вы должны добавить эти объекты учетных данных и адреса SIP для двух учетных записей.</span><span class="sxs-lookup"><span data-stu-id="67a67-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="67a67-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-кспресенце](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="67a67-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="67a67-125">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="67a67-125">Determining success or failure</span></span>

<span data-ttu-id="67a67-126">Если указанные пользователи могут обмениваться сведениями о присутствии, вы получите вывод, как показано ниже, и свойство результата помечено как **успешно.**</span><span class="sxs-lookup"><span data-stu-id="67a67-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="67a67-127">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="67a67-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="67a67-128">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="67a67-128">Result : Success</span></span>

<span data-ttu-id="67a67-129">Задержка: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="67a67-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="67a67-130">Ошибки</span><span class="sxs-lookup"><span data-stu-id="67a67-130">Error :</span></span>

<span data-ttu-id="67a67-131">Диагностик</span><span class="sxs-lookup"><span data-stu-id="67a67-131">Diagnosis :</span></span>

<span data-ttu-id="67a67-132">Если два пользователя не могут обмениваться сведениями о присутствии, результат будет показан в виде ошибки, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="67a67-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="67a67-133">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="67a67-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="67a67-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="67a67-134">Result : Failure</span></span>

<span data-ttu-id="67a67-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="67a67-135">Latency : 00:00:00</span></span>

<span data-ttu-id="67a67-136">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="67a67-136">Error : 404, Not Found</span></span>

<span data-ttu-id="67a67-137">Диагностика: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="67a67-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="67a67-138">Reason = универсальный код ресурса (URI) назначения не включен для SIP либо не</span><span class="sxs-lookup"><span data-stu-id="67a67-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="67a67-139">Существует.</span><span class="sxs-lookup"><span data-stu-id="67a67-139">exist.</span></span>

<span data-ttu-id="67a67-140">Microsoft. RTC. SignalR. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="67a67-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="67a67-141">Например, предыдущее выходное состояние не прошло проверку, так как по крайней мере одна из двух учетных записей пользователей недействительна: либо учетная запись не существует, либо она не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a67-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="67a67-142">Вы можете убедиться, что учетные записи существуют, и определить, включены ли они для Lync Server, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="67a67-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="67a67-143">Если при выполнении теста-Кспресенце происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="67a67-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="67a67-144">При включенном параметре "подробный" функция Test-Кспресенце будет возвращать пошаговые инструкции для каждого действия, которое он пытался войти на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a67-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="67a67-145">Например:</span><span class="sxs-lookup"><span data-stu-id="67a67-145">For example:</span></span>

<span data-ttu-id="67a67-146">Попадание в запрос на регистрацию для неизвестного</span><span class="sxs-lookup"><span data-stu-id="67a67-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="67a67-147">Действие "регистрация" завершено в течение "0,0345791" сек.</span><span class="sxs-lookup"><span data-stu-id="67a67-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="67a67-148">Начато действие "Селфсубскрибеактивити".</span><span class="sxs-lookup"><span data-stu-id="67a67-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="67a67-149">Действие "Селфсубскрибеактивити" завершено в течение "0,0041174" сек.</span><span class="sxs-lookup"><span data-stu-id="67a67-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="67a67-150">Начато действие "Субскрибепресенце".</span><span class="sxs-lookup"><span data-stu-id="67a67-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="67a67-151">Действие "Субскрибепресенце" завершено в течение "0,0038764" сек.</span><span class="sxs-lookup"><span data-stu-id="67a67-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="67a67-152">Начато действие "Публишпресенце".</span><span class="sxs-lookup"><span data-stu-id="67a67-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="67a67-153">Уведомление о присутствии исключения не получено в течение 25 сек.</span><span class="sxs-lookup"><span data-stu-id="67a67-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="67a67-154">произошла ошибка руинг рабочего процесса Microsoft. RTC. Синсетиктрансактионс. Workflow. Стпресенцеворкфлов.</span><span class="sxs-lookup"><span data-stu-id="67a67-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="67a67-155">Тот факт, что уведомление о присутствии не было получено в течение 25 секунд, может указывать на проблемы с сетью, препятствующие обмену данными.</span><span class="sxs-lookup"><span data-stu-id="67a67-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="67a67-156">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="67a67-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="67a67-157">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кспресенце:</span><span class="sxs-lookup"><span data-stu-id="67a67-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="67a67-158">Вы указали неверную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="67a67-158">You specified an incorrect user account.</span></span> <span data-ttu-id="67a67-159">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="67a67-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="67a67-160">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a67-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="67a67-161">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="67a67-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="67a67-162">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a67-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

