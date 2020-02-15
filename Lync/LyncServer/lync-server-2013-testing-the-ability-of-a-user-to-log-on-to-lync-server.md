---
title: 'Lync Server 2013: Проверка возможности входа пользователя на Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b40479bc11fc1f46062423d63876b33d9c179aa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="507d7-102">Проверка возможности входа пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="507d7-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="507d7-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="507d7-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="507d7-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="507d7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="507d7-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="507d7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="507d7-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="507d7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="507d7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="507d7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="507d7-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="507d7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="507d7-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="507d7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="507d7-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="507d7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="507d7-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="507d7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="507d7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="507d7-112">Description</span></span>

<span data-ttu-id="507d7-113">Командлет Test-CsRegistration позволяет убедиться, что пользователи в организации могут войти в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507d7-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="507d7-114">При выполнении командлета Test-CsRegistration командлет пытается войти в тестовый пользователь в Lync Server, а затем, если он был успешным, отсоединяется тестовый пользователь от системы.</span><span class="sxs-lookup"><span data-stu-id="507d7-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="507d7-115">Все это происходит без вмешательства пользователя и без влияния на фактических пользователей.</span><span class="sxs-lookup"><span data-stu-id="507d7-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="507d7-116">Например, предположим, что тестовая учетная запись sip:kenmyer@litwareinc.com соответствует реальному пользователю с действительной учетной записью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507d7-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="507d7-117">В этом случае тест будет проводиться без какого-либо вмешательства в работу реального пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="507d7-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="507d7-118">Когда тестовая учетная запись Ken Myer выйдет из системы, личная учетная запись Ken Myer останется в системе.</span><span class="sxs-lookup"><span data-stu-id="507d7-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="507d7-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="507d7-119">Running the test</span></span>

<span data-ttu-id="507d7-120">Командлет Test-CsRegistration можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507d7-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="507d7-121">Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя тестируемого пула регистратора Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507d7-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="507d7-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="507d7-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="507d7-123">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="507d7-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="507d7-124">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="507d7-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="507d7-125">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="507d7-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="507d7-126">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="507d7-126">Determining success or failure</span></span>

<span data-ttu-id="507d7-127">Если указанный пользователь может войти в систему, а затем выйти из нее с сервера Lync Server, будет выведен результат, подобный следующему, с помощью свойства Result, помеченного как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="507d7-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="507d7-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="507d7-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="507d7-129">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="507d7-129">Result : Success</span></span>

<span data-ttu-id="507d7-130">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="507d7-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="507d7-131">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="507d7-131">Error :</span></span>

<span data-ttu-id="507d7-132">Диагност</span><span class="sxs-lookup"><span data-stu-id="507d7-132">Diagnosis :</span></span>

<span data-ttu-id="507d7-133">Если указанный пользователь не может войти в систему или выйти из нее, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="507d7-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="507d7-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="507d7-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="507d7-135">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="507d7-135">Result : Failure</span></span>

<span data-ttu-id="507d7-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="507d7-136">Latency : 00:00:00</span></span>

<span data-ttu-id="507d7-137">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="507d7-137">Error : 404, Not Found</span></span>

<span data-ttu-id="507d7-138">Диагностика: ErrorCode = 1003, Source = ATL-CS-001. litwareinc. com, Reason = пользователь выполняет</span><span class="sxs-lookup"><span data-stu-id="507d7-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="507d7-139">не существует</span><span class="sxs-lookup"><span data-stu-id="507d7-139">not exist</span></span>

<span data-ttu-id="507d7-140">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="507d7-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="507d7-141">Например, предыдущие выходные данные почтовых состояний не пройдены, так как не удалось найти указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="507d7-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="507d7-142">Вы можете определить, является ли адрес SIP допустимым (и ли пользователь, которому назначен SIP-адрес, включен для Lync Server), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="507d7-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="507d7-143">Если Test-CsRegistration завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="507d7-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="507d7-144">Если включен параметр Verbose, командлет Test-CsRegistration возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507d7-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="507d7-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="507d7-145">For example:</span></span>

<span data-ttu-id="507d7-146">VERBOSE: начато действие "Register".</span><span class="sxs-lookup"><span data-stu-id="507d7-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="507d7-147">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="507d7-147">Sending Registration request:</span></span>

<span data-ttu-id="507d7-148">Целевое полное доменное имя = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="507d7-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="507d7-149">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="507d7-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="507d7-150">Порт регистратора = 5061.</span><span class="sxs-lookup"><span data-stu-id="507d7-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="507d7-151">Выбран тип проверки подлинности "доверенный".</span><span class="sxs-lookup"><span data-stu-id="507d7-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="507d7-152">Не удается зарегистрировать исключение "конечная точка не может быть зарегистрирована".</span><span class="sxs-lookup"><span data-stu-id="507d7-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="507d7-153">Просмотрите код ошибки для конкретной причины "при выполнении рабочего процесса Microsoft. RTC. SyntheticTransactions. Workflow. Стрегистрерворкфлов.</span><span class="sxs-lookup"><span data-stu-id="507d7-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="507d7-154">Стек вызовов исключения: в Microsoft. RTC. SignalR. SipAsyncResult'1. Сровиффаилед ()</span><span class="sxs-lookup"><span data-stu-id="507d7-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="507d7-155">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="507d7-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="507d7-156">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="507d7-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="507d7-157">Вы указали неправильную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="507d7-157">You specified an incorrect user account.</span></span> <span data-ttu-id="507d7-158">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="507d7-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="507d7-159">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507d7-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="507d7-160">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="507d7-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="507d7-161">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507d7-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="507d7-162">Указан недопустимый пул регистратора.</span><span class="sxs-lookup"><span data-stu-id="507d7-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="507d7-163">С помощью этой команды можно получить полные доменные имена пулов регистратора.</span><span class="sxs-lookup"><span data-stu-id="507d7-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="507d7-164">В настоящее время пул регистратора недоступен.</span><span class="sxs-lookup"><span data-stu-id="507d7-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="507d7-165">Попробуйте выполнить команду ping для пула, чтобы узнать, отвечает ли он:</span><span class="sxs-lookup"><span data-stu-id="507d7-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

