---
title: 'Lync Server 2013: Проверка возможности пользователя войти на сервер Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="0a40e-102">Проверка возможности пользователя войти на сервер Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a40e-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a40e-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0a40e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a40e-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="0a40e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0a40e-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="0a40e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a40e-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="0a40e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0a40e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a40e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a40e-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="0a40e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0a40e-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="0a40e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0a40e-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксрегистратион.</span><span class="sxs-lookup"><span data-stu-id="0a40e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="0a40e-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0a40e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0a40e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0a40e-112">Description</span></span>

<span data-ttu-id="0a40e-113">Командлет Test-Ксрегистратион позволяет удостовериться, что пользователи в вашей организации могут войти на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a40e-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="0a40e-114">При запуске test-Ксрегистратион командлет пытается войти в тестовый пользователь на Lync Server, а затем, если он успешно завершает работу, с помощью которого тестовый пользователь будет отключен от системы.</span><span class="sxs-lookup"><span data-stu-id="0a40e-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="0a40e-115">Все это происходит без взаимодействия с пользователем и без воздействия каких – либо реальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a40e-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="0a40e-116">Например, предположим, что проверка учетной записи sip:kenmyer@litwareinc.comа с реальным пользователем, у которого есть учетная запись сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a40e-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="0a40e-117">В этом случае тест будет проводиться без перерывов в работе Кен мер.</span><span class="sxs-lookup"><span data-stu-id="0a40e-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="0a40e-118">Когда Кен мер тестовая учетная запись выходит из системы, Кен мер человека останется на входе.</span><span class="sxs-lookup"><span data-stu-id="0a40e-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0a40e-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="0a40e-119">Running the test</span></span>

<span data-ttu-id="0a40e-120">Командлет Test-Ксрегистратион можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a40e-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="0a40e-121">Для выполнения этой проверки с помощью тестовой учетной записи необходимо указать полное доменное имя для тестируемого пула регистраторов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a40e-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="0a40e-122">Например:</span><span class="sxs-lookup"><span data-stu-id="0a40e-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="0a40e-123">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, содержащий имя учетной записи и пароль.</span><span class="sxs-lookup"><span data-stu-id="0a40e-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="0a40e-124">Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-Ксрегистратион:</span><span class="sxs-lookup"><span data-stu-id="0a40e-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="0a40e-125">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксрегистратион](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="0a40e-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0a40e-126">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="0a40e-126">Determining success or failure</span></span>

<span data-ttu-id="0a40e-127">Если указанный пользователь может войти на сервер Lync Server (а затем выйти из него), вы получите вывод примерно так, чтобы его свойство Result пометило как **успешное.**</span><span class="sxs-lookup"><span data-stu-id="0a40e-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="0a40e-128">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0a40e-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0a40e-129">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="0a40e-129">Result : Success</span></span>

<span data-ttu-id="0a40e-130">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="0a40e-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="0a40e-131">Ошибки</span><span class="sxs-lookup"><span data-stu-id="0a40e-131">Error :</span></span>

<span data-ttu-id="0a40e-132">Диагностик</span><span class="sxs-lookup"><span data-stu-id="0a40e-132">Diagnosis :</span></span>

<span data-ttu-id="0a40e-133">Если указанному пользователю не удается войти в систему или выйти из нее, результат будет показан в виде ошибки, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="0a40e-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="0a40e-134">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0a40e-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0a40e-135">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="0a40e-135">Result : Failure</span></span>

<span data-ttu-id="0a40e-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0a40e-136">Latency : 00:00:00</span></span>

<span data-ttu-id="0a40e-137">Ошибка: 404, не найдена</span><span class="sxs-lookup"><span data-stu-id="0a40e-137">Error : 404, Not Found</span></span>

<span data-ttu-id="0a40e-138">Диагностика: ErrorCode = 1003, источник = ATL-CS-001. плана litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="0a40e-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="0a40e-139">не существует</span><span class="sxs-lookup"><span data-stu-id="0a40e-139">not exist</span></span>

<span data-ttu-id="0a40e-140">Microsoft. RTC. SignalR. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="0a40e-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="0a40e-141">Например, в предыдущем выводе говорится, что тест завершился сбоем, так как указанный пользователь не найден.</span><span class="sxs-lookup"><span data-stu-id="0a40e-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="0a40e-142">Вы можете определить, является ли адрес SIP допустимым (и назначен ли пользователю этот адрес SIP для Lync Server), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0a40e-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="0a40e-143">Если при выполнении теста-Ксрегистратион происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="0a40e-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="0a40e-144">При включенном параметре "подробный" функция Test-Ксрегистратион будет возвращать пошаговые инструкции для каждого действия, которое он пытался войти на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a40e-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="0a40e-145">Например:</span><span class="sxs-lookup"><span data-stu-id="0a40e-145">For example:</span></span>

<span data-ttu-id="0a40e-146">ПОДРОБНЫЕ сведения: начато действие "регистрация".</span><span class="sxs-lookup"><span data-stu-id="0a40e-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="0a40e-147">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="0a40e-147">Sending Registration request:</span></span>

<span data-ttu-id="0a40e-148">Целевое полное доменное имя = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0a40e-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="0a40e-149">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0a40e-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="0a40e-150">Порт регистратора = 5061.</span><span class="sxs-lookup"><span data-stu-id="0a40e-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="0a40e-151">Выбран тип проверки подлинности "Trusted".</span><span class="sxs-lookup"><span data-stu-id="0a40e-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="0a40e-152">Исключение "конечная точка не может зарегистрироваться.</span><span class="sxs-lookup"><span data-stu-id="0a40e-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="0a40e-153">Просмотрите код ошибки для конкретной причины "произошла ошибка" во время выполнения рабочего процесса Microsoft. RTC. Синсетиктрансактионс. Workflow. Стрегистрерворкфлов.</span><span class="sxs-lookup"><span data-stu-id="0a40e-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="0a40e-154">Стек вызовов исключений: в Microsoft. RTC. SignalR. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="0a40e-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0a40e-155">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="0a40e-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="0a40e-156">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксрегистратион:</span><span class="sxs-lookup"><span data-stu-id="0a40e-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="0a40e-157">Вы указали неверную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a40e-157">You specified an incorrect user account.</span></span> <span data-ttu-id="0a40e-158">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0a40e-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="0a40e-159">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a40e-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="0a40e-160">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="0a40e-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="0a40e-161">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a40e-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="0a40e-162">Вы указали неправильный пул регистраторов.</span><span class="sxs-lookup"><span data-stu-id="0a40e-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="0a40e-163">Вы можете вернуть полные доменные имена для пулов регистратора с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="0a40e-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="0a40e-164">Пул регистраторов в настоящее время недоступен.</span><span class="sxs-lookup"><span data-stu-id="0a40e-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="0a40e-165">Попробуйте выполнить команду ping для пула, чтобы узнать, отвечает ли он.</span><span class="sxs-lookup"><span data-stu-id="0a40e-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

