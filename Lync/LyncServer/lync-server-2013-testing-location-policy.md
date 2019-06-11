---
title: 'Lync Server 2013: проверка политики расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="65359-102">Проверка политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65359-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65359-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="65359-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65359-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="65359-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="65359-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="65359-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65359-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="65359-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="65359-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65359-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65359-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="65359-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="65359-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="65359-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="65359-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кслокатионполици.</span><span class="sxs-lookup"><span data-stu-id="65359-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="65359-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="65359-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="65359-112">Описание</span><span class="sxs-lookup"><span data-stu-id="65359-112">Description</span></span>

<span data-ttu-id="65359-113">Командлет Test-Кслокатионполици удостоверяет, что политика расположения назначена пользователю.</span><span class="sxs-lookup"><span data-stu-id="65359-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="65359-114">Политика Location используется для применения параметров, которые связаны с функциональностью E9-1-1 и адресом клиента.</span><span class="sxs-lookup"><span data-stu-id="65359-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="65359-115">Политика расположения определяет, разрешено ли пользователю E9-1-1, и, если вы ответили "Да", каково поведение вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="65359-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="65359-116">Например, вы можете использовать политику расположения, чтобы определить, какой номер является вызовом экстренной помощи (911 в США), следует ли автоматически уведомлять корпоративную безопасность, а также как перенаправлять этот звонок.</span><span class="sxs-lookup"><span data-stu-id="65359-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="65359-117">Вы можете проверить политики расположения для пользователей или подсетей сети.</span><span class="sxs-lookup"><span data-stu-id="65359-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="65359-118">Если вы пропустили тест для подсети (указав значение параметра подсети), командлет попытается разрешить политику расположения для этой подсети.</span><span class="sxs-lookup"><span data-stu-id="65359-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="65359-119">Если подсеть не назначена ни одной политики расположения, будет извлекаться политика расположения для настроенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="65359-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="65359-120">Если политика подсети получена успешно, выходные данные будут содержать значение Локатионполицитагид, которое начинается с подсети тагид.</span><span class="sxs-lookup"><span data-stu-id="65359-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="65359-121">Если политика расположения для подсети не найдена, Локатионполицитагид будет начинаться с User-тагид.</span><span class="sxs-lookup"><span data-stu-id="65359-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="65359-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="65359-122">Running the test</span></span>

<span data-ttu-id="65359-123">Командлет Test-Кслокатионполици можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65359-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="65359-124">Для выполнения этой проверки с помощью тестовой учетной записи нужно просто указать полное доменное имя для тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65359-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="65359-125">Например:</span><span class="sxs-lookup"><span data-stu-id="65359-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="65359-126">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, содержащий имя учетной записи и пароль.</span><span class="sxs-lookup"><span data-stu-id="65359-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="65359-127">Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-Кслокатионполици:</span><span class="sxs-lookup"><span data-stu-id="65359-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="65359-128">Дополнительные сведения можно найти в справочной документации по командлету [Test-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="65359-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="65359-129">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="65359-129">Determining success or failure</span></span>

<span data-ttu-id="65359-130">Если указанный пользователь имеет действующую политику расположения, вы получите вывод, как показано ниже, и свойство Result, помеченное как **успешно.**</span><span class="sxs-lookup"><span data-stu-id="65359-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="65359-131">Енханцедемерженцисервицесенаблед: true</span><span class="sxs-lookup"><span data-stu-id="65359-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="65359-132">Локатионполицитагид: User-тагид</span><span class="sxs-lookup"><span data-stu-id="65359-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="65359-133">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65359-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65359-134">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="65359-134">Result : Success</span></span>

<span data-ttu-id="65359-135">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="65359-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="65359-136">Ошибки</span><span class="sxs-lookup"><span data-stu-id="65359-136">Error :</span></span>

<span data-ttu-id="65359-137">Диагностик</span><span class="sxs-lookup"><span data-stu-id="65359-137">Diagnosis :</span></span>

<span data-ttu-id="65359-138">Если для указанного пользователя не удается найти действующую политику расположения, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="65359-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="65359-139">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65359-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65359-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="65359-140">Result : Failure</span></span>

<span data-ttu-id="65359-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="65359-141">Latency : 00:00:00</span></span>

<span data-ttu-id="65359-142">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="65359-142">Error : 404, Not Found</span></span>

<span data-ttu-id="65359-143">Диагностика: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="65359-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="65359-144">Reason = универсальный код ресурса (URI) назначения не включен для SIP либо не</span><span class="sxs-lookup"><span data-stu-id="65359-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="65359-145">Существует.</span><span class="sxs-lookup"><span data-stu-id="65359-145">exist.</span></span>

<span data-ttu-id="65359-146">Microsoft. RTC. SignalR. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="65359-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="65359-147">В предыдущем выводе говорится, что тест завершился сбоем, так как указан недопустимый пользователь: учетная запись не существует или пользователь не включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65359-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="65359-148">Вы можете проверить правильность учетной записи и определить, включена ли эта учетная запись для NM-OCS-14-3, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="65359-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="65359-149">Если при выполнении теста-Кслокатионполици происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="65359-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="65359-150">При включенном параметре "подробный" тест-Кслокатионполици будет возвращать пошаговые учетные записи для каждого действия, которое он пытался проверить в политике расположения.</span><span class="sxs-lookup"><span data-stu-id="65359-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="65359-151">Например, этот вывод указывает на то, что серверу Lync Server не удалось войти в тестовый пользователь, возможно, из-за того, что был введен недопустимый пароль.</span><span class="sxs-lookup"><span data-stu-id="65359-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="65359-152">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="65359-152">Sending Registration request :</span></span>

<span data-ttu-id="65359-153">Целевое полное доменное имя = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65359-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="65359-154">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65359-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="65359-155">Порт регистратора = 5061</span><span class="sxs-lookup"><span data-stu-id="65359-155">Registrar Port = 5061</span></span>

<span data-ttu-id="65359-156">Выбран тип проверки подлинности "Ива".</span><span class="sxs-lookup"><span data-stu-id="65359-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="65359-157">Регистрация в соответствии с SIP/ATL-CS-001. плана litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="65359-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65359-158">Действие "регистрация" завершено в течение "0,0601795" сек.</span><span class="sxs-lookup"><span data-stu-id="65359-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="65359-159">Исключение "вход был отклонен".</span><span class="sxs-lookup"><span data-stu-id="65359-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="65359-160">Убедитесь в том, что используются правильные учетные данные, а учетная запись активна.</span><span class="sxs-lookup"><span data-stu-id="65359-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="65359-161">произошла ошибка рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="65359-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="65359-162">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="65359-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="65359-163">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кслокатионполици:</span><span class="sxs-lookup"><span data-stu-id="65359-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="65359-164">Указана недействительная учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="65359-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="65359-165">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="65359-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="65359-166">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65359-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="65359-167">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="65359-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="65359-168">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65359-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

