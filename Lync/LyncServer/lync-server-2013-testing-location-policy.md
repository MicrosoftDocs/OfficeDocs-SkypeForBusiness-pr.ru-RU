---
title: 'Lync Server 2013: проверка политики расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cd477b02aa261b762f728ca15d296f49dfbac1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535996"
---
# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="a2899-102">Проверка политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2899-102">Testing location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2899-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a2899-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2899-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="a2899-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a2899-105">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="a2899-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2899-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="a2899-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a2899-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2899-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2899-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="a2899-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a2899-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a2899-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a2899-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="a2899-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="a2899-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2899-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a2899-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a2899-112">Description</span></span>

<span data-ttu-id="a2899-113">Командлет Test-CsLocationPolicy проверяет, назначена ли политика расположения пользователю.</span><span class="sxs-lookup"><span data-stu-id="a2899-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="a2899-114">Политика местоположения используется для определения параметров, относящихся к функциям службы E9-1-1 и местоположению клиента.</span><span class="sxs-lookup"><span data-stu-id="a2899-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="a2899-115">Политика расположения определяет, включен ли для пользователя E9-1-1, и, если ответ имеет значение "Да", что такое поведение экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="a2899-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="a2899-116">Например, можно использовать политику расположения, чтобы определить, какой номер выполняет экстренные вызовы (911 в США), следует ли автоматически уведомлять корпоративный уровень безопасности и как перенаправлять вызов.</span><span class="sxs-lookup"><span data-stu-id="a2899-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="a2899-117">Тестировать политики местоположения можно на пользователях или на подсетях.</span><span class="sxs-lookup"><span data-stu-id="a2899-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="a2899-118">Если запустить тест для подсети (указав значение для параметра Subnet), командлет попытается обнаружить политику местоположения для этой подсети.</span><span class="sxs-lookup"><span data-stu-id="a2899-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="a2899-119">Если подсети не назначена политика местоположения, будет извлечена политика местоположения для заданного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a2899-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="a2899-120">Если политика подсети успешно получена, выходные данные будут включать значение Локатионполицитагид, начинающееся с подсети тагид.</span><span class="sxs-lookup"><span data-stu-id="a2899-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="a2899-121">Если политика местоположения для подсети не найдена, значение LocationPolicyTagID будет начинаться со строки user-tagid.</span><span class="sxs-lookup"><span data-stu-id="a2899-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a2899-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="a2899-122">Running the test</span></span>

<span data-ttu-id="a2899-123">Командлет Test-CsLocationPolicy можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2899-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="a2899-124">Чтобы выполнить эту проверку с помощью тестовой учетной записи, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2899-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="a2899-125">Например:</span><span class="sxs-lookup"><span data-stu-id="a2899-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="a2899-126">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="a2899-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="a2899-127">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="a2899-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a2899-128">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="a2899-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a2899-129">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="a2899-129">Determining success or failure</span></span>

<span data-ttu-id="a2899-130">Если указанный пользователь имеет действительную политику расположения, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success.**</span><span class="sxs-lookup"><span data-stu-id="a2899-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="a2899-131">Енханцедемерженцисервицесенаблед: true</span><span class="sxs-lookup"><span data-stu-id="a2899-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="a2899-132">Локатионполицитагид: User — тагид</span><span class="sxs-lookup"><span data-stu-id="a2899-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="a2899-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2899-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a2899-134">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="a2899-134">Result : Success</span></span>

<span data-ttu-id="a2899-135">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="a2899-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="a2899-136">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="a2899-136">Error :</span></span>

<span data-ttu-id="a2899-137">Диагност</span><span class="sxs-lookup"><span data-stu-id="a2899-137">Diagnosis :</span></span>

<span data-ttu-id="a2899-138">Если для указанного пользователя не удается найти действительную политику расположения, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a2899-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a2899-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2899-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a2899-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="a2899-140">Result : Failure</span></span>

<span data-ttu-id="a2899-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a2899-141">Latency : 00:00:00</span></span>

<span data-ttu-id="a2899-142">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="a2899-142">Error : 404, Not Found</span></span>

<span data-ttu-id="a2899-143">Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="a2899-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="a2899-144">Reason = конечный URI либо не включен для SIP, либо не</span><span class="sxs-lookup"><span data-stu-id="a2899-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="a2899-145">есть.</span><span class="sxs-lookup"><span data-stu-id="a2899-145">exist.</span></span>

<span data-ttu-id="a2899-146">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="a2899-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="a2899-147">Предыдущие выходные данные построили, что не удалось выполнить тест, так как указанный пользователь не является допустимым: либо учетная запись не существует, либо для пользователя не был включен сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2899-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="a2899-148">Вы можете проверить допустимость учетной записи и определить, включена ли эта учетная запись для NM-OCS-14-3, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a2899-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="a2899-149">Если Test-CsLocationPolicy завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="a2899-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="a2899-150">Если включен параметр Verbose, Test-CsLocationPolicy будет возвращать пошаговые учетные записи всех действий, которые он пытался проверить в политике расположения.</span><span class="sxs-lookup"><span data-stu-id="a2899-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="a2899-151">Например, эти выходные данные показывают, что серверу Lync Server не удалось выполнить вход в систему тестового пользователя, вероятно, из-за неправильного пароля:</span><span class="sxs-lookup"><span data-stu-id="a2899-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="a2899-152">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="a2899-152">Sending Registration request :</span></span>

<span data-ttu-id="a2899-153">Целевое полное доменное имя = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2899-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="a2899-154">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2899-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="a2899-155">Порт регистратора = 5061</span><span class="sxs-lookup"><span data-stu-id="a2899-155">Registrar Port = 5061</span></span>

<span data-ttu-id="a2899-156">Выбран тип проверки подлинности "Ива".</span><span class="sxs-lookup"><span data-stu-id="a2899-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="a2899-157">Регистрация с использованием SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="a2899-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a2899-158">Действие ' Register ' завершено в ' 0,0601795 ' сек.</span><span class="sxs-lookup"><span data-stu-id="a2899-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="a2899-159">Исключение "при входе в систему было отклонено.</span><span class="sxs-lookup"><span data-stu-id="a2899-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="a2899-160">Убедитесь, что используются правильные учетные данные, а учетная запись активна. "</span><span class="sxs-lookup"><span data-stu-id="a2899-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="a2899-161">При выполнении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a2899-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a2899-162">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="a2899-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="a2899-163">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="a2899-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="a2899-164">Указана недопустимая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="a2899-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="a2899-165">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a2899-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a2899-166">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2899-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="a2899-167">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="a2899-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a2899-168">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2899-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

