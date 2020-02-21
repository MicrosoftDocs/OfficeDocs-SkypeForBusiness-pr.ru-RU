---
title: 'Lync Server 2013: тестирование однорангового аудио-и видеозвонка'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5283f588315d06387ed2d441f138538cd13ca3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="f242d-102">Тестирование однорангового аудио-и видеозвонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f242d-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f242d-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f242d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f242d-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="f242d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f242d-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="f242d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f242d-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="f242d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f242d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f242d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f242d-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="f242d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f242d-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f242d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f242d-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsP2PAV.</span><span class="sxs-lookup"><span data-stu-id="f242d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="f242d-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f242d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f242d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f242d-112">Description</span></span>

<span data-ttu-id="f242d-113">Test-CsP2PAV используется для определения того, может ли пользователь иметь возможность участвовать в одноранговой беседе A/V.</span><span class="sxs-lookup"><span data-stu-id="f242d-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="f242d-114">Чтобы протестировать этот сценарий, командлет начинает с ведения журнала для двух пользователей в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f242d-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="f242d-115">Предположим, что вход обоих пользователей выполнен успешно, а первый пользователь приглашает второго пользователя в аудио-видео беседу.</span><span class="sxs-lookup"><span data-stu-id="f242d-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="f242d-116">Второй пользователь принимает приглашение, проверяется подключение между двумя пользователями, а затем вызов завершается, а тестовые пользователи выходят из системы.</span><span class="sxs-lookup"><span data-stu-id="f242d-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="f242d-117">Test-CsP2PAV не проводит функцию "аудио"/"V".</span><span class="sxs-lookup"><span data-stu-id="f242d-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="f242d-118">Обмен мультимедийными данными между тестовыми пользователями не осуществляется.</span><span class="sxs-lookup"><span data-stu-id="f242d-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="f242d-119">Вместо этого командлет проверяет, могут ли быть выполнены соответствующие подключения, и могут ли два пользователя совершать такой вызов.</span><span class="sxs-lookup"><span data-stu-id="f242d-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="f242d-120">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="f242d-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f242d-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="f242d-121">Running the test</span></span>

<span data-ttu-id="f242d-122">Командлет Test-CsP2PAV можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетных записей двух пользователей с включенной поддержкой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f242d-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f242d-123">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f242d-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f242d-124">Например:</span><span class="sxs-lookup"><span data-stu-id="f242d-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f242d-125">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f242d-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f242d-126">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsP2PAV:</span><span class="sxs-lookup"><span data-stu-id="f242d-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f242d-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="f242d-127">Determining success or failure</span></span>

<span data-ttu-id="f242d-128">Если два тестовых пользователя могут выполнить одноранговый вызов A/V, вы получите выходные данные, аналогичные приведенным ниже, со свойством Result, помеченным как **Success.**</span><span class="sxs-lookup"><span data-stu-id="f242d-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f242d-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f242d-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f242d-130">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f242d-130">Result : Success</span></span>

<span data-ttu-id="f242d-131">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="f242d-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="f242d-132">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="f242d-132">Error :</span></span>

<span data-ttu-id="f242d-133">Диагност</span><span class="sxs-lookup"><span data-stu-id="f242d-133">Diagnosis :</span></span>

<span data-ttu-id="f242d-134">Если тестовые пользователи не могут выполнить вызов, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f242d-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f242d-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f242d-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f242d-136">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="f242d-136">Result : Failure</span></span>

<span data-ttu-id="f242d-137">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f242d-137">Latency : 00:00:00</span></span>

<span data-ttu-id="f242d-138">Ошибка: 480, временно недоступна</span><span class="sxs-lookup"><span data-stu-id="f242d-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="f242d-139">Диагностика: ErrorCode = 15030, Source = ATL-CS-001. litwareinc. com, Reason = Failed</span><span class="sxs-lookup"><span data-stu-id="f242d-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="f242d-140">порядок маршрутизации в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f242d-140">to route to Exchange Server</span></span>

<span data-ttu-id="f242d-141">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="f242d-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f242d-142">Например, предыдущие выходные данные почтовых состояний завершились сбоем, так как не удалось связаться с сервером Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="f242d-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="f242d-143">Это сообщение об ошибке обычно указывает на проблему, связанную с настройкой единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="f242d-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="f242d-144">Если не удается выполнить команду Test-CsP2PAV, вам может потребоваться повторить проверку, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="f242d-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="f242d-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-verbose</span><span class="sxs-lookup"><span data-stu-id="f242d-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="f242d-146">Когда включается параметр Verbose, командлет Test-CsP2PAV возвращает пошаговое описание каждого выполняемого действия, как проверяло возможность входа в систему на Lync Server для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f242d-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f242d-147">Например, предположим, что тест завершился со следующей диагностикой:</span><span class="sxs-lookup"><span data-stu-id="f242d-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="f242d-148">ErrorCode = 6003, Source = ATL-CS-001. litwareinc. com, Reason = не поддерживается в диалоговом окне запроса</span><span class="sxs-lookup"><span data-stu-id="f242d-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="f242d-149">Если вы перезапустите Test-CsP2PAV и включили параметр Verbose, вы получите результат, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="f242d-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="f242d-150">VERBOSE: начато действие "Register".</span><span class="sxs-lookup"><span data-stu-id="f242d-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="f242d-151">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="f242d-151">Sending Registration request:</span></span>

<span data-ttu-id="f242d-152">Целевое полное доменное имя = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f242d-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f242d-153">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f242d-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f242d-154">Порт регистратора = 5062.</span><span class="sxs-lookup"><span data-stu-id="f242d-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="f242d-155">Выбран тип проверки подлинности "Ива".</span><span class="sxs-lookup"><span data-stu-id="f242d-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f242d-156">Исключение "не удалось зарегистрировать конечную точку.</span><span class="sxs-lookup"><span data-stu-id="f242d-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="f242d-157">Обратитесь к разделу ErrorCode по определенному причине.</span><span class="sxs-lookup"><span data-stu-id="f242d-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="f242d-158">возникла во время выполнения рабочего процесса Microsoft. RTC. SyntheticTransactions. Workflows. STP2PAVWorkflow.</span><span class="sxs-lookup"><span data-stu-id="f242d-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="f242d-159">Несмотря на то, что в результате анализа результатов может быть непросто очевидно, вы увидите, что был указан недопустимый порт регистратора (порт 5062).</span><span class="sxs-lookup"><span data-stu-id="f242d-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="f242d-160">В свою очередь это привело к сбою теста.</span><span class="sxs-lookup"><span data-stu-id="f242d-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f242d-161">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="f242d-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="f242d-162">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsP2PAV:</span><span class="sxs-lookup"><span data-stu-id="f242d-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="f242d-163">Указана недопустимая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="f242d-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="f242d-164">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f242d-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="f242d-165">Get – CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="f242d-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="f242d-166">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f242d-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f242d-167">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f242d-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f242d-168">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f242d-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

