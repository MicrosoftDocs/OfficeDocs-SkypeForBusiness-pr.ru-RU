---
title: 'Lync Server 2013: Проверка правил голосовой связи, маршрутов и политик'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="47244-102">Проверка правил, маршрутов и политик голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47244-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47244-103">_**Тема последнего изменения:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="47244-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47244-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="47244-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="47244-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="47244-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47244-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="47244-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="47244-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47244-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47244-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="47244-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="47244-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="47244-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="47244-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксвоицеусер.</span><span class="sxs-lookup"><span data-stu-id="47244-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="47244-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="47244-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="47244-112">Описание</span><span class="sxs-lookup"><span data-stu-id="47244-112">Description</span></span>

<span data-ttu-id="47244-113">Когда пользователь выполняет телефонный звонок, маршрут, по которому выполняется звонок, зависит от политик и абонентских тарифов, назначенных этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="47244-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="47244-114">Если вы получили адрес SIP и номер телефона пользователя, командлет Test-Ксвоицеусер проверяет, может ли пользователь выполнить Звонок на этот номер.</span><span class="sxs-lookup"><span data-stu-id="47244-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="47244-115">Если проверка выполнена успешно, функция Test-Ксвоицеусер возвращает следующее:</span><span class="sxs-lookup"><span data-stu-id="47244-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="47244-116">Число преобразовано в формат E. 164 (в соответствии с абонентской панелью пользователя).</span><span class="sxs-lookup"><span data-stu-id="47244-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="47244-117">Правило нормализации, которое предоставляет этот перевод</span><span class="sxs-lookup"><span data-stu-id="47244-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="47244-118">Используемый маршрут голоса (на основе приоритета маршрута);</span><span class="sxs-lookup"><span data-stu-id="47244-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="47244-119">Использование телефона, связанного с политикой голосовой связи пользователя, с голосовым маршрутом.</span><span class="sxs-lookup"><span data-stu-id="47244-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="47244-120">Test-Ксвоицеусер позволяет определить, будет ли конкретный номер телефона маршрутизироваться и переводиться должным образом, и может помочь устранить проблемы, связанные с вызовами, которые возникают у отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="47244-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="47244-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="47244-121">Running the test</span></span>

<span data-ttu-id="47244-122">При запуске командлета Test-Ксвоицеусер необходимо предоставить два фрагмента информации: номер набираемого номера (Диаледнумбер) и удостоверение тестируемой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="47244-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="47244-123">Например, эта команда проверяет возможность пользователя, у которого есть SIP-адрес sip:kenmyer@litwareinc.com, звонить на номер телефона + 1206555-1219:</span><span class="sxs-lookup"><span data-stu-id="47244-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="47244-124">Номер телефона должен быть отформатирован так, как вы планируете набрать его.</span><span class="sxs-lookup"><span data-stu-id="47244-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="47244-125">Например, если пользователи, как правило, не набирает номер 1 перед тем, как звонить по междугородней связи, следует использовать следующий формат:</span><span class="sxs-lookup"><span data-stu-id="47244-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="47244-126">Разумеется, в этом случае тест завершится ошибкой, если у вас нет правила нормализации, позволяющего правильно перевести число 2065551219 в формат телефона E. 164, который используется в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47244-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="47244-127">Дополнительные сведения можно найти в разделе справки Командлет New-Ксвоиценормализатионруле.</span><span class="sxs-lookup"><span data-stu-id="47244-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="47244-128">Если вы хотите выполнить этот же тест для каждой учетной записи пользователя, вы можете использовать команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="47244-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="47244-129">Дополнительные сведения можно найти в справочной документации по командлету Test-Ксвоицеусер.</span><span class="sxs-lookup"><span data-stu-id="47244-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="47244-130">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="47244-130">Determining success or failure</span></span>

<span data-ttu-id="47244-131">Если проверка выполнена успешно (то есть, если пользователь может выполнить телефонный звонок на указанный номер), на выходе будут показаны такие данные, как переведенный номер телефона, а также соответствующее правило нормализации и голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="47244-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="47244-132">Транслатеднумбер Матчингруле Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="47244-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="47244-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="47244-133"></span></span>

<span data-ttu-id="47244-134">\+12065551219 дескрипти...    Локальный Локалрауте</span><span class="sxs-lookup"><span data-stu-id="47244-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="47244-135">Из-за ограничений на экран Windows PowerShell по крайней мере некоторые возвращенные сведения (особенно важно, полное описание соответствующего правила нормализации) могут не отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="47244-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="47244-136">Если вы заинтересованы в успешном или неуспешном выполнении теста, это может быть неважно.</span><span class="sxs-lookup"><span data-stu-id="47244-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="47244-137">Если вы хотите просмотреть полные сведения о возвращенных данных, перечислите выходные данные в командлет Format-List при выполнении теста.</span><span class="sxs-lookup"><span data-stu-id="47244-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="47244-138">Это приведет к отображению выходных данных в более удобном формате для чтения:</span><span class="sxs-lookup"><span data-stu-id="47244-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="47244-139">Транслатеднумбер: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="47244-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="47244-140">Матчингруле: описание =; Шаблон = ^ (\\d{11}) $; Перевод = + $1;</span><span class="sxs-lookup"><span data-stu-id="47244-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="47244-141">Name = prefix ALL; Исинтерналекстенсион = false</span><span class="sxs-lookup"><span data-stu-id="47244-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="47244-142">Фирсматчинграуте: Локалрауте</span><span class="sxs-lookup"><span data-stu-id="47244-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="47244-143">Матчингусаже: local</span><span class="sxs-lookup"><span data-stu-id="47244-143">MatchingUsage : Local</span></span>

<span data-ttu-id="47244-144">Если тест не проходит проверку, Ксвоицеусер будет возвращать пустой набор значений свойств.</span><span class="sxs-lookup"><span data-stu-id="47244-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="47244-145">Транслатеднумбер Матчингруле Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="47244-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="47244-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="47244-146"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="47244-147">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="47244-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="47244-148">Существует несколько причин, по которым может произойти сбой командлета Test-Ксвоицеусер: возможно, отсутствует правило нормализации, которое может перевести указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="47244-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="47244-149">Возможно, возникли проблемы с голосовым маршрутом.</span><span class="sxs-lookup"><span data-stu-id="47244-149">There could be problems with the voice route.</span></span> <span data-ttu-id="47244-150">Возможно, у вас возникла ошибка конфигурации для абонентской группы, назначенной пользователю.</span><span class="sxs-lookup"><span data-stu-id="47244-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="47244-151">По этой причине при запуске командлета Test-Ксвоицеусер может потребоваться включить параметр Verbose.</span><span class="sxs-lookup"><span data-stu-id="47244-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="47244-152">После включения подробного командлета Test-Ксвоицеусер будет выдавать подробные сведения обо всех действиях, выполненных при проведении проверок.</span><span class="sxs-lookup"><span data-stu-id="47244-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="47244-153">Например, вы можете увидеть шаги, аналогичные указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="47244-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="47244-154">VERBOSE: Поиск пользователей с удостоверением "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="47244-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="47244-155">VERBOSE: Загрузка абонентской группы: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="47244-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="47244-156">Дополнительные сведения можно найти в разделе действия, которые можно выполнить для выявления причины сбоя.</span><span class="sxs-lookup"><span data-stu-id="47244-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="47244-157">Например, подробный вывод показывает, что тестируемому пользователю назначена абонентская группа RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="47244-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="47244-158">Если тест завершился сбоем, следующим логическим шагом будет проверка того, что RedmondDialPlan может перевести предоставленный телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="47244-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47244-159">См. также</span><span class="sxs-lookup"><span data-stu-id="47244-159">See Also</span></span>


[<span data-ttu-id="47244-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="47244-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

