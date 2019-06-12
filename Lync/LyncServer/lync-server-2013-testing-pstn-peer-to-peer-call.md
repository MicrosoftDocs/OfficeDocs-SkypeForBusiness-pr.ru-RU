---
title: 'Lync Server 2013: Проверка однорангового соединения PSTN с одноранговым узлом'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="633a0-102">Проверка однорангового соединения PSTN с одноранговым подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="633a0-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="633a0-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="633a0-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="633a0-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="633a0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="633a0-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="633a0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="633a0-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="633a0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="633a0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="633a0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="633a0-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="633a0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="633a0-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="633a0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="633a0-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кспстнпиртопиркалл.</span><span class="sxs-lookup"><span data-stu-id="633a0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="633a0-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="633a0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="633a0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="633a0-112">Description</span></span>

<span data-ttu-id="633a0-113">Командлет Test-Кспстнпиртопиркалл проверит возможность того, что пользователи смогут выполнить одноранговый Звонок по шлюзу КОММУТИРУЕМой телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="633a0-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="633a0-114">При вызове Test-Кспстнпиртопиркалл командлет сначала попытается выполнить вход двух тестовых пользователей на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="633a0-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="633a0-115">Если вход в систему выполнен успешно, командлет получит пользователю 1 попытку позвонить пользователю 2 через шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="633a0-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="633a0-116">Проверка-Кспстнпиртопиркалл сделает этот звонок с помощью абонентской группы, политики голосовой связи и других параметров политики и конфигурации, назначенных тестовому пользователю.</span><span class="sxs-lookup"><span data-stu-id="633a0-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="633a0-117">Если тест пройдет по плану, командлет проверит, что пользователь 2 смог ответить на звонок, а затем выполнит выход из тестовых учетных записей из системы.</span><span class="sxs-lookup"><span data-stu-id="633a0-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="633a0-118">Test-Кспстнпиртопиркалл делает фактический телефонный звонок, который проверяет, что соединение может быть установлено, а также передает коды DTMF по сети, чтобы определить, может ли мультимедиа быть отправлено по этому подключению.</span><span class="sxs-lookup"><span data-stu-id="633a0-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="633a0-119">На звонок отвечает сам командлет, и вам не нужно вручную завершать звонок.</span><span class="sxs-lookup"><span data-stu-id="633a0-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="633a0-120">(Это значит, что никто не должен отвечать на звонки, а затем повесить трубку, которая была вызвана.)</span><span class="sxs-lookup"><span data-stu-id="633a0-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="633a0-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="633a0-121">Running the test</span></span>

<span data-ttu-id="633a0-122">Командлет Test-Кспстнпиртопиркалл можно выполнить с помощью пары предварительно настроенных тестовых учетных записей (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетные записи любых двух пользователей, которые включены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="633a0-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="633a0-123">Для выполнения этой проверки с помощью тестовых учетных записей нужно просто указать полное доменное имя для тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="633a0-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="633a0-124">Например:</span><span class="sxs-lookup"><span data-stu-id="633a0-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="633a0-125">Для выполнения этой проверки с использованием фактических учетных записей пользователей необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="633a0-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="633a0-126">После вызова Test-Кспстнпиртопиркалл вы должны добавить эти объекты учетных данных и адреса SIP для двух учетных записей.</span><span class="sxs-lookup"><span data-stu-id="633a0-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="633a0-127">Дополнительные сведения можно найти в справочной документации по командлету [Test-кспстнпиртопиркалл](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="633a0-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="633a0-128">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="633a0-128">Determining success or failure</span></span>

<span data-ttu-id="633a0-129">Если указанные пользователи могут выполнить одноранговый звонок, вы получите вывод, как показано ниже, и свойство Result, помеченное как **успешно.**</span><span class="sxs-lookup"><span data-stu-id="633a0-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="633a0-130">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="633a0-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="633a0-131">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="633a0-131">Result : Success</span></span>

<span data-ttu-id="633a0-132">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="633a0-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="633a0-133">Ошибки</span><span class="sxs-lookup"><span data-stu-id="633a0-133">Error :</span></span>

<span data-ttu-id="633a0-134">Диагностик</span><span class="sxs-lookup"><span data-stu-id="633a0-134">Diagnosis :</span></span>

<span data-ttu-id="633a0-135">Если указанные пользователи не могут выполнить одноранговый звонок, результат будет показан как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="633a0-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="633a0-136">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="633a0-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="633a0-137">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="633a0-137">Result : Failure</span></span>

<span data-ttu-id="633a0-138">Задержка: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="633a0-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="633a0-139">Ошибка: 403, запрещено</span><span class="sxs-lookup"><span data-stu-id="633a0-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="633a0-140">Диагностика: ErrorCode = 12001, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="633a0-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="633a0-141">Причина = политика пользователя не содержит использование маршрутных номеров</span><span class="sxs-lookup"><span data-stu-id="633a0-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="633a0-142">В предыдущем выводе говорится, что тест завершился сбоем, так как политика голосовой связи, назначенная по крайней мере одному из указанных пользователей, не содержит использование телефона.</span><span class="sxs-lookup"><span data-stu-id="633a0-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="633a0-143">(Использование телефона применяет политики голосовой связи для голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="633a0-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="633a0-144">Без политики голосовой связи и соответствующего голосового маршрута вы не сможете звонить по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="633a0-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="633a0-145">Если при выполнении теста-Кспстнпиртопиркалл происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="633a0-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="633a0-146">При включенном параметре "подробный" функция Test-Кспстнпиртопиркалл будет возвращать пошаговые инструкции для каждого действия, которое он пытался войти на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="633a0-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="633a0-147">Например, эти выходные данные указывают на то, что неполадки в сети не препятствуют подключению к КТСОП.</span><span class="sxs-lookup"><span data-stu-id="633a0-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="633a0-148">Установка голосового видеозвонка на "SIP: +12065551219@litwareinc.com; user = Phone".</span><span class="sxs-lookup"><span data-stu-id="633a0-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="633a0-149">В сети получено исключение "404 (не найдено), и операция завершилась сбоем.</span><span class="sxs-lookup"><span data-stu-id="633a0-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="633a0-150">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="633a0-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="633a0-151">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кспстнпиртопиркалл:</span><span class="sxs-lookup"><span data-stu-id="633a0-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="633a0-152">Указана недействительная учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="633a0-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="633a0-153">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="633a0-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="633a0-154">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="633a0-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="633a0-155">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="633a0-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="633a0-156">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="633a0-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="633a0-157">Политика голосовой связи, назначенная указанному пользователю, не может использоваться в качестве использования КТСОП.</span><span class="sxs-lookup"><span data-stu-id="633a0-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="633a0-158">Вы можете определить политику голосовой связи, назначенную для пользователя, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="633a0-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="633a0-159">Затем вы можете определить использование PSTN (если таковые есть), назначенные этой политике, используя следующую команду, которая извлекает сведения о политике голосовой связи для пользователя Редмондвоицеполици:</span><span class="sxs-lookup"><span data-stu-id="633a0-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

