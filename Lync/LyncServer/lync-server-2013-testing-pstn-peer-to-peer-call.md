---
title: 'Lync Server 2013: тестирование однорангового вызова PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c172ea79e646e9deec1c56e792d4e7c4df3a26
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="1b1e7-102">Тестирование однорангового звонка PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b1e7-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b1e7-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1b1e7-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b1e7-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="1b1e7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1b1e7-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="1b1e7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b1e7-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="1b1e7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1b1e7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b1e7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b1e7-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="1b1e7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1b1e7-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1b1e7-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsPstnPeerToPeerCall.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="1b1e7-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1b1e7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1b1e7-112">Description</span></span>

<span data-ttu-id="1b1e7-113">Командлет Test-CsPstnPeerToPeerCall проверяет возможность, с помощью которой пользователи могут выполнять одноранговые вызовы по шлюзу коммутируемой телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="1b1e7-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="1b1e7-114">При вызове командлета Test-CsPstnPeerToPeerCall командлет сначала попытается выполнить вход двух тестовых пользователей на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="1b1e7-115">При условии, что входы выполняются успешно, в командлете пользователь 1 пытается позвонить пользователю 2 по шлюзу PSTN.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="1b1e7-116">Test-CsPstnPeerToPeerCall сделает этот вызов с помощью абонентской группы, политики голосовой связи, а также других параметров политики и конфигурации, назначенных тестовому пользователю.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="1b1e7-117">Если тест проходит запланированно, командлет проверяет, чтобы пользователь 2 мог ответить на звонок, а затем выйдите из системы как тестовые учетные записи из системы.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="1b1e7-118">Test-CsPstnPeerToPeerCall выполняет фактический телефонный звонок, который проверяет, можно ли выполнить подключение, а также передает коды DTMF по сети, чтобы определить, можно ли отправлять мультимедиа через подключение.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="1b1e7-119">На вызов отвечает сам командлет, и нет необходимости вручную завершать вызов.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="1b1e7-120">(То есть, ни один из них не должен отвечать, а затем прервать вызов.)</span><span class="sxs-lookup"><span data-stu-id="1b1e7-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1b1e7-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="1b1e7-121">Running the test</span></span>

<span data-ttu-id="1b1e7-122">Командлет Test-CsPstnPeerToPeerCall можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетных записей двух пользователей с включенной поддержкой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="1b1e7-123">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="1b1e7-124">Например:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="1b1e7-125">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="1b1e7-126">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsPstnPeerToPeerCall:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="1b1e7-127">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="1b1e7-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1b1e7-128">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="1b1e7-128">Determining success or failure</span></span>

<span data-ttu-id="1b1e7-129">Если указанные пользователи могут выполнить одноранговый вызов, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="1b1e7-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="1b1e7-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1b1e7-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1b1e7-131">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="1b1e7-131">Result : Success</span></span>

<span data-ttu-id="1b1e7-132">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="1b1e7-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="1b1e7-133">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="1b1e7-133">Error :</span></span>

<span data-ttu-id="1b1e7-134">Диагност</span><span class="sxs-lookup"><span data-stu-id="1b1e7-134">Diagnosis :</span></span>

<span data-ttu-id="1b1e7-135">Если указанные пользователи не могут выполнить одноранговый звонок, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1b1e7-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1b1e7-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1b1e7-137">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="1b1e7-137">Result : Failure</span></span>

<span data-ttu-id="1b1e7-138">Задержка: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="1b1e7-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="1b1e7-139">Ошибка: 403, запрещено</span><span class="sxs-lookup"><span data-stu-id="1b1e7-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="1b1e7-140">Диагностика: ErrorCode = 12001, Source = ATL – CS – 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="1b1e7-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="1b1e7-141">Reason = политика пользователя не содержит использования маршрута по телефону</span><span class="sxs-lookup"><span data-stu-id="1b1e7-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="1b1e7-142">В предыдущих выходных данных говорится, что тест завершился ошибкой, так как политика голосовой связи, назначенная по крайней мере одному из указанных пользователей, не включает использование телефона.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="1b1e7-143">(Использование телефона применяет политики голосовой связи для маршрутов голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="1b1e7-144">Без политики голосовой связи и соответствующего голосового маршрута нельзя совершать звонки по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="1b1e7-145">Если Test-CsPstnPeerToPeerCall завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="1b1e7-146">Если включен параметр Verbose, командлет Test-CsPstnPeerToPeerCall возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="1b1e7-147">Например, эти выходные данные показывают, что неполадки в сети препятствуют подключению с помощью PSTN:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="1b1e7-148">Установка голосового видеозвонка в "SIP: + 12065551219@litwareinc. com; user = Phone".</span><span class="sxs-lookup"><span data-stu-id="1b1e7-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="1b1e7-149">Из сети получено исключение "ответ 404 (не найдено"); операция завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1b1e7-150">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="1b1e7-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="1b1e7-151">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsPstnPeerToPeerCall:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="1b1e7-152">Указана недопустимая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="1b1e7-153">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1b1e7-154">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="1b1e7-155">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="1b1e7-156">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="1b1e7-157">Политика голосовой связи, назначенная указанному пользователю, не имеет действительного использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="1b1e7-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="1b1e7-158">Вы можете определить политику голосовой связи, назначенную пользователю, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="1b1e7-159">Затем вы можете определить использование PSTN (если они есть), назначенные этой политике, с помощью следующей команды, которая получает сведения о политике голосовой связи "на пользователя" RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="1b1e7-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

