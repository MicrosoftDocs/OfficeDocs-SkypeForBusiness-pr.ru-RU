---
title: 'Lync Server 2013: тестирование возможности обмена мгновенными сообщениями между двумя пользователями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 145a2849d8b87f0f19559583e94edb5e895f89db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500496"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="f3691-102">Возможность тестирования обмена мгновенными сообщениями между двумя пользователями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3691-102">Testing ability to IM between two users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3691-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f3691-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3691-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="f3691-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f3691-105">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="f3691-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3691-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="f3691-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f3691-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3691-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3691-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="f3691-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f3691-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f3691-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f3691-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsIM.</span><span class="sxs-lookup"><span data-stu-id="f3691-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="f3691-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f3691-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f3691-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f3691-112">Description</span></span>

<span data-ttu-id="f3691-113">Командлет Test-CsIM проверяет, может ли пользователь обмениваться мгновенными сообщениями с помощью командлета Test.</span><span class="sxs-lookup"><span data-stu-id="f3691-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="f3691-114">При вызове командлет Test-CsIM начинает работу, пытаясь войти в систему на сервере Lync Server с помощью учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3691-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="f3691-115">При условии, что два входа успешно выполнены, командлет запускает сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="f3691-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="f3691-116">(Пользователь 1 приглашает пользователя 2 в сеанс обмена мгновенными сообщениями, а пользователь 2 принимает приглашение.) После проверки того, что обмен сообщениями между двумя пользователями может осуществляться, Test-CsIM завершает сеанс обмена мгновенными сообщениями и выполняет вход обоих пользователей из системы.</span><span class="sxs-lookup"><span data-stu-id="f3691-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="f3691-117">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f3691-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f3691-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="f3691-118">Running the Test</span></span>

<span data-ttu-id="f3691-119">Командлет Test-CsIM можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для запуска тестов Lync Server) или учетных записей двух пользователей, для которых включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3691-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f3691-120">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3691-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f3691-121">Например:</span><span class="sxs-lookup"><span data-stu-id="f3691-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f3691-122">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f3691-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f3691-123">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f3691-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="f3691-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f3691-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f3691-125">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="f3691-125">Determining Success or Failure</span></span>

<span data-ttu-id="f3691-126">Если два пользователя могут выполнить сеанс обмена мгновенными сообщениями, будет выведен результат, подобный следующему, при этом свойство Result помечается как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="f3691-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f3691-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3691-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3691-128">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f3691-128">Result : Success</span></span>

<span data-ttu-id="f3691-129">Задержка: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="f3691-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="f3691-130">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="f3691-130">Error :</span></span>

<span data-ttu-id="f3691-131">Диагност</span><span class="sxs-lookup"><span data-stu-id="f3691-131">Diagnosis :</span></span>

<span data-ttu-id="f3691-132">Если тестовые пользователи не могут завершить сеанс, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="f3691-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f3691-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3691-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3691-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="f3691-134">Result : Failure</span></span>

<span data-ttu-id="f3691-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f3691-135">Latency : 00:00:00</span></span>

<span data-ttu-id="f3691-136">Ошибка: 504, время ожидания сервера</span><span class="sxs-lookup"><span data-stu-id="f3691-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="f3691-137">Диагностика: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = видите</span><span class="sxs-lookup"><span data-stu-id="f3691-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="f3691-138">код отклика и фраза причины.</span><span class="sxs-lookup"><span data-stu-id="f3691-138">response code and reason phrase.</span></span>

<span data-ttu-id="f3691-139">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="f3691-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f3691-140">Например, предыдущие выходные данные почтовых состояний не пройдены, так как не удалось найти указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3691-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="f3691-141">Можно определить, является ли адрес SIP допустимым (и ли пользователь, которому был назначен SIP-адрес, включен для Lync Server), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f3691-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="f3691-142">Если Test-CsIM завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="f3691-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f3691-143">Если включен параметр Verbose, Test-CsIM будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности двух тестовых пользователей принять участие в сеансе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f3691-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="f3691-144">Например, приведенный ниже пример выходных данных, возникающих при наличии неправильного набора учетных данных пользователя (в данном случае, неправильного пароля), предоставляется для Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f3691-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="f3691-145">Отправка запроса на регистрацию:</span><span class="sxs-lookup"><span data-stu-id="f3691-145">Sending Registration request :</span></span>

<span data-ttu-id="f3691-146">Целевое полное доменное имя = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3691-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f3691-147">SIP адрес пользователя = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3691-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f3691-148">Порт регистратора = 5061</span><span class="sxs-lookup"><span data-stu-id="f3691-148">Registrar Port = 5061</span></span>

<span data-ttu-id="f3691-149">Выбран тип проверки подлинности "Ива".</span><span class="sxs-lookup"><span data-stu-id="f3691-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f3691-150">Регистрация с использованием SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="f3691-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3691-151">Действие ' Register ' завершено в ' 0,0601795 ' сек.</span><span class="sxs-lookup"><span data-stu-id="f3691-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="f3691-152">Исключение "при входе в систему было отклонено.</span><span class="sxs-lookup"><span data-stu-id="f3691-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="f3691-153">Убедитесь, что используются правильные учетные данные, а учетная запись активна. "</span><span class="sxs-lookup"><span data-stu-id="f3691-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="f3691-154">При выполнении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f3691-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f3691-155">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="f3691-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="f3691-156">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f3691-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="f3691-157">Указана недопустимая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3691-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="f3691-158">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f3691-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f3691-159">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3691-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f3691-160">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f3691-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f3691-161">Если для свойства Enabled задано значение false, то в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3691-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f3691-162">Служба обмена мгновенными сообщениями может быть недоступна.</span><span class="sxs-lookup"><span data-stu-id="f3691-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="f3691-163">С помощью Lync Server можно настроить систему таким образом, чтобы мгновенные сообщения не были доступны, если не удается получить доступ к базе данных архивации.</span><span class="sxs-lookup"><span data-stu-id="f3691-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="f3691-164">Это можно проверить, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f3691-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="f3691-165">Если для Блокконарчивефаилуре задано значение true, то следует определить, доступна ли база данных архивации.</span><span class="sxs-lookup"><span data-stu-id="f3691-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="f3691-166">Вы можете вернуть расположения баз данных архивации с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="f3691-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="f3691-167">Сервер архивации может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="f3691-167">The Archiving server might not be available.</span></span> <span data-ttu-id="f3691-168">С помощью этой команды можно получить полное доменное имя серверов архивации:</span><span class="sxs-lookup"><span data-stu-id="f3691-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="f3691-169">После этого вы можете проверить связь с соответствующим сервером, чтобы убедиться, что он доступен.</span><span class="sxs-lookup"><span data-stu-id="f3691-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="f3691-170">Пример:</span><span class="sxs-lookup"><span data-stu-id="f3691-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

