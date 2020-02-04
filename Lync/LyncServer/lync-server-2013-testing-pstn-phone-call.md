---
title: 'Lync Server 2013: Проверка КОММУТИРУЕМого телефонного звонка'
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
ms.openlocfilehash: 8095b4b0bb6aa4e6920d291c3fde3885ae6bfb03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="6d54e-102">Проверка телефонной связи PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d54e-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d54e-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6d54e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d54e-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="6d54e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6d54e-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="6d54e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d54e-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="6d54e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6d54e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d54e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d54e-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="6d54e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6d54e-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="6d54e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6d54e-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксрегистратион.</span><span class="sxs-lookup"><span data-stu-id="6d54e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="6d54e-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6d54e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6d54e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6d54e-112">Description</span></span>

<span data-ttu-id="6d54e-113">Командлет Test-Кспстнаутбаундкалл проверяет способность пользователя совершить звонок на номер телефона, находящийся в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="6d54e-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="6d54e-114">При запуске test-Кспстнаутбаундкалл командлет сначала пытается записать тестовый пользователь на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d54e-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="6d54e-115">Если вход будет выполнен успешно, командлет попытается выполнить телефонный звонок через шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="6d54e-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="6d54e-116">Этот телефонный звонок будет выполняться с использованием абонентской группы, политики голосовой связи и других политик и параметров, назначенных тестовой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6d54e-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="6d54e-117">При ответе на звонок командлет отправляет Многочастотные коды с несколькими частотами (DTMF) по сети для проверки подключения к носителю.</span><span class="sxs-lookup"><span data-stu-id="6d54e-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="6d54e-118">При проведении проверки тест-Кспстнаутбаундкалл выполнит фактический телефонный звонок: на целевом телефоне будет звонить, и для успешного завершения теста должен быть дан ответ.</span><span class="sxs-lookup"><span data-stu-id="6d54e-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="6d54e-119">Этот звонок также должен завершиться администратором вручную.</span><span class="sxs-lookup"><span data-stu-id="6d54e-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6d54e-120">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="6d54e-120">Running the test</span></span>

<span data-ttu-id="6d54e-121">Командлет Test-Кспстнаутбаундкалл можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d54e-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="6d54e-122">Для выполнения этой проверки с помощью тестовой учетной записи необходимо указать полное доменное имя тестируемого пула сервера Lync и телефонный номер PSTN.</span><span class="sxs-lookup"><span data-stu-id="6d54e-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="6d54e-123">Например:</span><span class="sxs-lookup"><span data-stu-id="6d54e-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="6d54e-124">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, содержащий имя учетной записи и пароль.</span><span class="sxs-lookup"><span data-stu-id="6d54e-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="6d54e-125">Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-Кспстнаутбаундкалл:</span><span class="sxs-lookup"><span data-stu-id="6d54e-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6d54e-126">Дополнительные сведения можно найти в справочной документации по командлету [Test-кспстнаутбаундкалл](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="6d54e-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6d54e-127">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="6d54e-127">Determining success or failure</span></span>

<span data-ttu-id="6d54e-128">Если заданный пользователь может позвонить, и при ответе на него будет получено сообщение о том, что свойство результата помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="6d54e-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="6d54e-129">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6d54e-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6d54e-130">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="6d54e-130">Result : Success</span></span>

<span data-ttu-id="6d54e-131">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="6d54e-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="6d54e-132">Ошибки</span><span class="sxs-lookup"><span data-stu-id="6d54e-132">Error :</span></span>

<span data-ttu-id="6d54e-133">Диагностик</span><span class="sxs-lookup"><span data-stu-id="6d54e-133">Diagnosis :</span></span>

<span data-ttu-id="6d54e-134">Если указанный пользователь не может позвонить или звонок не отвечает, результат будет показан как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="6d54e-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6d54e-135">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6d54e-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6d54e-136">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="6d54e-136">Result : Failure</span></span>

<span data-ttu-id="6d54e-137">Задержка: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="6d54e-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="6d54e-138">Ошибка: 403, запрещено</span><span class="sxs-lookup"><span data-stu-id="6d54e-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="6d54e-139">Диагностика: ErrorCode = 12001, Source = ATL-CS-001. плана litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="6d54e-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="6d54e-140">Политика не содержит использование маршрутных номеров</span><span class="sxs-lookup"><span data-stu-id="6d54e-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="6d54e-141">В предыдущем выводе говорится, что тест завершился сбоем, так как политика голосовой связи, назначенная указанному пользователю, не содержит использование телефона.</span><span class="sxs-lookup"><span data-stu-id="6d54e-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="6d54e-142">(Использование телефона применяет политики голосовой связи для голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="6d54e-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="6d54e-143">Без политики голосовой связи и соответствующего голосового маршрута вы не можете звонить по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="6d54e-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="6d54e-144">Если при выполнении теста-Кспстнаутбаундкалл происходит сбой, может потребоваться повторное выполнение теста, на этот раз включая параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="6d54e-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="6d54e-145">При включенном параметре "подробный" функция Test-Кспстнаутбаундкалл будет возвращать пошаговые инструкции для каждого действия, которое он пытался войти на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d54e-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="6d54e-146">Например, эти выходные данные указывают на то, что неполадки в сети не препятствуют подключению к КТСОП.</span><span class="sxs-lookup"><span data-stu-id="6d54e-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="6d54e-147">Установка голосового видеозвонка на "SIP: + 12065551219@litwareinc. com; user = Phone".</span><span class="sxs-lookup"><span data-stu-id="6d54e-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="6d54e-148">В сети получено исключение "404 (не найдено), и операция завершилась сбоем.</span><span class="sxs-lookup"><span data-stu-id="6d54e-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6d54e-149">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="6d54e-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="6d54e-150">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кспстнаутбаундкалл:</span><span class="sxs-lookup"><span data-stu-id="6d54e-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="6d54e-151">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d54e-151">You specified an invalid user account.</span></span> <span data-ttu-id="6d54e-152">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6d54e-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="6d54e-153">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d54e-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="6d54e-154">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="6d54e-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="6d54e-155">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d54e-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="6d54e-156">Политика голосовой связи, назначенная указанному пользователю, не может использоваться в качестве использования КТСОП.</span><span class="sxs-lookup"><span data-stu-id="6d54e-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="6d54e-157">Вы можете определить политику голосовой связи, назначенную для пользователя, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="6d54e-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="6d54e-158">Затем вы можете определить использование PSTN (если таковые есть), назначенные этой политике, используя следующую команду, которая извлекает сведения о политике голосовой связи для пользователя Редмондвоицеполици:</span><span class="sxs-lookup"><span data-stu-id="6d54e-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

