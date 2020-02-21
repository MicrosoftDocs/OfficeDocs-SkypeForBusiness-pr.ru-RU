---
title: 'Lync Server 2013: тестирование телефонного звонка PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c9c0b0441ea31e2419101aba188c33b0bbfd70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="72b36-102">Тестирование телефонного звонка PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72b36-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72b36-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="72b36-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72b36-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="72b36-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="72b36-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="72b36-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72b36-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="72b36-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="72b36-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72b36-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72b36-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="72b36-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="72b36-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="72b36-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="72b36-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="72b36-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="72b36-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="72b36-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="72b36-112">Описание</span><span class="sxs-lookup"><span data-stu-id="72b36-112">Description</span></span>

<span data-ttu-id="72b36-113">Командлет Test-CsPstnOutboundCall тестирует способность пользователя совершать вызовы на телефонный номер, находящийся в PSTN.</span><span class="sxs-lookup"><span data-stu-id="72b36-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="72b36-114">При выполнении командлета Test-CsPstnOutboundCall сначала выполняется попытка входа тестового пользователя в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72b36-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="72b36-115">Если вход выполнен успешно, командлет попробует позвонить через шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="72b36-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="72b36-116">Этот телефонный звонок будет выполняться с помощью абонентской группы, политики голосовой связи и других политик и параметров, назначенных тестовой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="72b36-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="72b36-117">При ответе на вызов командлет отправляет Многочастотные коды многочастотного набора (DTMF) через сеть для проверки возможности подключения к мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="72b36-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="72b36-118">При проведении проверки тест-CsPstnOutboundCall будет совершать фактический телефонный звонок: на целевом телефоне будет выдаваться сообщение об успешном завершении проверки.</span><span class="sxs-lookup"><span data-stu-id="72b36-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="72b36-119">Этот вызов также должен закончить администратором вручную.</span><span class="sxs-lookup"><span data-stu-id="72b36-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="72b36-120">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="72b36-120">Running the test</span></span>

<span data-ttu-id="72b36-121">Командлет Test-CsPstnOutboundCall можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72b36-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="72b36-122">Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя тестируемого пула Lync Server и вызываемый телефонный номер PSTN.</span><span class="sxs-lookup"><span data-stu-id="72b36-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="72b36-123">Например:</span><span class="sxs-lookup"><span data-stu-id="72b36-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="72b36-124">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="72b36-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="72b36-125">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsPstnOutboundCall:</span><span class="sxs-lookup"><span data-stu-id="72b36-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="72b36-126">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="72b36-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="72b36-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="72b36-127">Determining success or failure</span></span>

<span data-ttu-id="72b36-128">Если указанный пользователь может совершать вызов, и при ответе на него будет получено сообщение о том, что свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="72b36-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="72b36-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72b36-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72b36-130">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="72b36-130">Result : Success</span></span>

<span data-ttu-id="72b36-131">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="72b36-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="72b36-132">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="72b36-132">Error :</span></span>

<span data-ttu-id="72b36-133">Диагност</span><span class="sxs-lookup"><span data-stu-id="72b36-133">Diagnosis :</span></span>

<span data-ttu-id="72b36-134">Если указанный пользователь не может выполнить вызов или ответ на него не получен, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="72b36-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="72b36-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72b36-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72b36-136">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="72b36-136">Result : Failure</span></span>

<span data-ttu-id="72b36-137">Задержка: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="72b36-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="72b36-138">Ошибка: 403, запрещено</span><span class="sxs-lookup"><span data-stu-id="72b36-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="72b36-139">Диагностика: ErrorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="72b36-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="72b36-140">Политика не содержит использования маршрута по телефону</span><span class="sxs-lookup"><span data-stu-id="72b36-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="72b36-141">В предыдущих выходных данных говорится, что тест завершился ошибкой, так как политика голосовой связи, назначенная указанному пользователю, не включает использование телефона.</span><span class="sxs-lookup"><span data-stu-id="72b36-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="72b36-142">(Использование телефона применяет политики голосовой связи для маршрутов голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="72b36-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="72b36-143">Без политики голосовой связи и соответствующего маршрута голосовой связи вы не можете совершать звонки по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="72b36-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="72b36-144">Если не удается выполнить команду Test-CsPstnOutboundCall, вам может потребоваться повторить проверку, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="72b36-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="72b36-145">Если включен параметр Verbose, командлет Test-CsPstnOutboundCall возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72b36-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="72b36-146">Например, эти выходные данные показывают, что неполадки в сети препятствуют подключению с помощью PSTN:</span><span class="sxs-lookup"><span data-stu-id="72b36-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="72b36-147">Установка голосового видеозвонка в "SIP: + 12065551219@litwareinc. com; user = Phone".</span><span class="sxs-lookup"><span data-stu-id="72b36-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="72b36-148">Из сети получено исключение "ответ 404 (не найдено"); операция завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="72b36-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="72b36-149">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="72b36-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="72b36-150">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsPstnOutboundCall:</span><span class="sxs-lookup"><span data-stu-id="72b36-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="72b36-151">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="72b36-151">You specified an invalid user account.</span></span> <span data-ttu-id="72b36-152">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="72b36-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="72b36-153">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72b36-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="72b36-154">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="72b36-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="72b36-155">Если для свойства Enabled задано значение false, то в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72b36-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="72b36-156">Политика голосовой связи, назначенная указанному пользователю, не имеет действительного использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="72b36-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="72b36-157">Вы можете определить политику голосовой связи, назначенную пользователю, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="72b36-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="72b36-158">Затем вы можете определить использование PSTN (если они есть), назначенные этой политике, с помощью следующей команды, которая получает сведения о политике голосовой связи "на пользователя" RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="72b36-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

