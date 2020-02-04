---
title: 'Lync Server 2013: Проверка аудио-и видеоконференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89bb8f38ea650bf64179b917b227d7ccaaf10791
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="28ebb-102">Проверка аудио-и видеоконференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28ebb-102">Validating audio/video conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28ebb-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="28ebb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28ebb-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="28ebb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="28ebb-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="28ebb-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28ebb-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="28ebb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="28ebb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28ebb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28ebb-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="28ebb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="28ebb-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="28ebb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="28ebb-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксавконференце.</span><span class="sxs-lookup"><span data-stu-id="28ebb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="28ebb-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28ebb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="28ebb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28ebb-112">Description</span></span>

<span data-ttu-id="28ebb-113">Командлет Test-Ксавконференце проверяет, могут ли два тестовых пользователя участвовать в аудио-или видеоконференции (A/V).</span><span class="sxs-lookup"><span data-stu-id="28ebb-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="28ebb-114">При запуске командлета два пользователя вошли в систему.</span><span class="sxs-lookup"><span data-stu-id="28ebb-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="28ebb-115">После того как они будут успешно вошли в систему, первый пользователь создаст Конференц-связь, а затем ждет, пока второй пользователь присоединится к этой Конференции.</span><span class="sxs-lookup"><span data-stu-id="28ebb-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="28ebb-116">После краткого обмена данными Конференция удаляется, а два теста пользователя выводятся из сеанса.</span><span class="sxs-lookup"><span data-stu-id="28ebb-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="28ebb-117">Обратите внимание на то, что Test-Ксавконференце не проводит фактическую конференцию/V между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="28ebb-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="28ebb-118">Вместо этого командлет проверяет, что два пользователя могут выполнять все необходимые подключения для проведения такой конференции.</span><span class="sxs-lookup"><span data-stu-id="28ebb-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="28ebb-119">Дополнительные примеры для этой команды можно найти на странице [Test-ксавконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="28ebb-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="28ebb-120">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="28ebb-120">Running the test</span></span>

<span data-ttu-id="28ebb-121">Командлет Test-Ксавконференце можно выполнить с помощью пары предварительно настроенных тестовых учетных записей (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетные записи любых двух пользователей, которые включены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28ebb-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="28ebb-122">Для выполнения этой проверки с помощью тестовых учетных записей нужно просто указать полное доменное имя для тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28ebb-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="28ebb-123">Например:</span><span class="sxs-lookup"><span data-stu-id="28ebb-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="28ebb-124">Для выполнения этой проверки с использованием фактических учетных записей пользователей необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="28ebb-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="28ebb-125">После этого вы должны добавить эти объекты учетных данных и адреса SIP для двух учетных записей при вызове Test-Ксавконференце:</span><span class="sxs-lookup"><span data-stu-id="28ebb-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="28ebb-126">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксавконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="28ebb-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="28ebb-127">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="28ebb-127">Determining Success or Failure</span></span>

<span data-ttu-id="28ebb-128">Если указанные пользователи могут успешно выполнить Конференц-связь между собой, вы получите вывод примерно так, чтобы свойство Result пометило **"успешно".**</span><span class="sxs-lookup"><span data-stu-id="28ebb-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="28ebb-129">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28ebb-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="28ebb-130">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="28ebb-130">Result : Success</span></span>

<span data-ttu-id="28ebb-131">Задержка: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="28ebb-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="28ebb-132">Ошибки</span><span class="sxs-lookup"><span data-stu-id="28ebb-132">Error :</span></span>

<span data-ttu-id="28ebb-133">Диагностик</span><span class="sxs-lookup"><span data-stu-id="28ebb-133">Diagnosis :</span></span>

<span data-ttu-id="28ebb-134">Если пользователи не могут выполнить конференцию, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="28ebb-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="28ebb-135">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28ebb-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="28ebb-136">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="28ebb-136">Result : Failure</span></span>

<span data-ttu-id="28ebb-137">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="28ebb-137">Latency : 00:00:00</span></span>

<span data-ttu-id="28ebb-138">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="28ebb-138">Error : 404, Not Found</span></span>

<span data-ttu-id="28ebb-139">Диагностика: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="28ebb-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="28ebb-140">Reason = универсальный код ресурса (URI) назначения не включен для SIP либо не</span><span class="sxs-lookup"><span data-stu-id="28ebb-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="28ebb-141">Существует.</span><span class="sxs-lookup"><span data-stu-id="28ebb-141">exist.</span></span>

<span data-ttu-id="28ebb-142">Microsoft. RTC. SignalR. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="28ebb-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="28ebb-143">Например, предыдущее выходное состояние не прошло проверку, так как по крайней мере одна из двух учетных записей пользователей была недействительной из-за того, что учетная запись не существует или учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28ebb-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="28ebb-144">Для проверки существования двух тестовых учетных записей и того, включены ли они в Lync Server, можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28ebb-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="28ebb-145">Если при выполнении теста-Ксавконференце происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="28ebb-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="28ebb-146">При включенном параметре "подробный" Ксавконференце возвращает пошаговые учетные записи для каждого действия, которое он попытался принять, когда вы проверили возможность участия указанных пользователей на Конференции AV.</span><span class="sxs-lookup"><span data-stu-id="28ebb-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="28ebb-147">Например, предположим, что тест завершается сбоем и вы получаете следующую диагностику.</span><span class="sxs-lookup"><span data-stu-id="28ebb-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="28ebb-148">ErrorCode = 1008, Source = акцесспрокси. плана litwareinc. com, причина — не удалось разрешить DNS-запись SRV</span><span class="sxs-lookup"><span data-stu-id="28ebb-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="28ebb-149">При повторном выполнении теста с помощью параметра подробных данных пошаговые инструкции будут возвращены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="28ebb-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="28ebb-150">ПОДРОБНЫЕ сведения: начато действие "регистрация".</span><span class="sxs-lookup"><span data-stu-id="28ebb-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="28ebb-151">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="28ebb-151">Sending Registration request:</span></span>

<span data-ttu-id="28ebb-152">Целевое полное доменное имя = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28ebb-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="28ebb-153">SIP адрес пользователя = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28ebb-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="28ebb-154">Порт регистратора = 5061.</span><span class="sxs-lookup"><span data-stu-id="28ebb-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="28ebb-155">Выбран тип проверки подлинности "Trusted".</span><span class="sxs-lookup"><span data-stu-id="28ebb-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="28ebb-156">Начато действие "регистрация".</span><span class="sxs-lookup"><span data-stu-id="28ebb-156">'Register' activity started.</span></span>

<span data-ttu-id="28ebb-157">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="28ebb-157">Sending Registration request:</span></span>

<span data-ttu-id="28ebb-158">Целевое полное доменное имя = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28ebb-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="28ebb-159">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28ebb-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="28ebb-160">Порт регистратора = 5061.</span><span class="sxs-lookup"><span data-stu-id="28ebb-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="28ebb-161">Выбран тип проверки подлинности "Trusted".</span><span class="sxs-lookup"><span data-stu-id="28ebb-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="28ebb-162">Исключение "не удалось зарегистрировать конечную точку".</span><span class="sxs-lookup"><span data-stu-id="28ebb-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="28ebb-163">Ознакомьтесь с ErrorCode по конкретной причине.</span><span class="sxs-lookup"><span data-stu-id="28ebb-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="28ebb-164">произошла ошибка в рабочем процессе</span><span class="sxs-lookup"><span data-stu-id="28ebb-164">occurred during Workflow</span></span>

<span data-ttu-id="28ebb-165">Последняя строка в этом выходных данных указывает на то, что пользователь sip:kenmyer@litwareinc.com не смог зарегистрироваться в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28ebb-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="28ebb-166">Это означает, что необходимо убедиться в том, что адрес SIP sip:kenmyer@litwareinc.com действителен и что связанный пользователь включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28ebb-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="28ebb-167">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="28ebb-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="28ebb-168">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксавконференце:</span><span class="sxs-lookup"><span data-stu-id="28ebb-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="28ebb-169">Указана недействительная учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="28ebb-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="28ebb-170">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28ebb-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="28ebb-171">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28ebb-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="28ebb-172">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="28ebb-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="28ebb-173">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28ebb-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

