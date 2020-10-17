---
title: 'Lync Server 2013: Тестирование правил голосовой связи, маршрутов и политик'
description: 'Lync Server 2013: Тестирование правил голосовой связи, маршрутов и политик.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf205ac2585298dfc5347d93e382e8bbda9f3ff4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557045"
---
# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="a93f1-103">Проверка правил голосовой связи, маршрутов и политик в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93f1-103">Test voice rules, routes, and policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a93f1-104">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a93f1-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a93f1-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="a93f1-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a93f1-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="a93f1-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a93f1-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="a93f1-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a93f1-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a93f1-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a93f1-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="a93f1-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a93f1-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a93f1-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a93f1-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="a93f1-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="a93f1-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a93f1-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a93f1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a93f1-113">Description</span></span>

<span data-ttu-id="a93f1-114">Когда пользователь выполняет телефонный звонок, маршрут, по которому выполняется звонок, зависит от политик и абонентских планов, назначенных этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="a93f1-114">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="a93f1-115">Если вы задаете SIP адрес и номер телефона пользователя, командлет Test-CsVoiceUser проверяет, может ли пользователь выполнить вызов по этому номеру.</span><span class="sxs-lookup"><span data-stu-id="a93f1-115">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="a93f1-116">Если проверка прошла успешно, Test-CsVoiceUser возвращает следующее:</span><span class="sxs-lookup"><span data-stu-id="a93f1-116">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="a93f1-117">Число преобразуется в формат E. 164 (на основе абонентской группы пользователя)</span><span class="sxs-lookup"><span data-stu-id="a93f1-117">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="a93f1-118">Правило нормализации, которое предоставляет этот перевод</span><span class="sxs-lookup"><span data-stu-id="a93f1-118">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="a93f1-119">Используемый маршрут голосовых вызовов (на основе приоритета маршрута);</span><span class="sxs-lookup"><span data-stu-id="a93f1-119">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="a93f1-120">Использование телефона, с помощью которого политика голосовой связи пользователя привязывается к маршруту голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a93f1-120">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="a93f1-121">Test-CsVoiceUser позволяет определить, будет ли конкретный номер телефона маршрутизироваться и транслироваться должным образом, и может помочь устранить проблемы, связанные с вызовами, которые возникают у отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a93f1-121">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a93f1-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="a93f1-122">Running the test</span></span>

<span data-ttu-id="a93f1-123">При запуске командлета Test-CsVoiceUser необходимо указать два фрагмента информации: номер набираемого номера (DialedNumber) и идентификатор тестируемой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="a93f1-123">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="a93f1-124">Например, эта команда проверяет способность пользователя, имеющего адрес SIP sip:kenmyer@litwareinc.com, совершать вызов на номер телефона + 1206555-1219:</span><span class="sxs-lookup"><span data-stu-id="a93f1-124">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="a93f1-125">Номер телефона должен быть отформатирован так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="a93f1-125">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="a93f1-126">Например, если пользователи обычно не набирать номер 1 перед выполнением междугородного звонка, используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="a93f1-126">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="a93f1-127">Конечно, в этом случае тест завершится с ошибками, если у вас нет правила нормализации, которое может правильно перевести число 2065551219 в формат телефона E. 164, используемый Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a93f1-127">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="a93f1-128">Для получения дополнительных сведений обратитесь к разделу справки New-CsVoiceNormalizationRule командлету.</span><span class="sxs-lookup"><span data-stu-id="a93f1-128">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="a93f1-129">Если вы хотите выполнить такой же тест для каждой учетной записи пользователя, можно использовать команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="a93f1-129">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="a93f1-130">Для получения дополнительных сведений обратитесь к справочной документации по командлету Test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="a93f1-130">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a93f1-131">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="a93f1-131">Determining success or failure</span></span>

<span data-ttu-id="a93f1-132">Если проверка успешно завершена (то есть, если пользователь может совершать телефонный звонок по указанному номеру), на выходе будут отображаться такие сведения, как переведенный номер телефона, а также соответствующее правило нормализации и маршрут голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a93f1-132">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="a93f1-133">Транслатеднумбер Матчингруле Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="a93f1-133">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="a93f1-134">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="a93f1-134">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="a93f1-135">\+12065551219 дескрипти...    Локальная LocalRoute</span><span class="sxs-lookup"><span data-stu-id="a93f1-135">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="a93f1-136">Из-за ограничений экрана Windows PowerShell по крайней мере некоторые возвращенные сведения (особенно часто полное описание совпадающего правила нормализации) могут не отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="a93f1-136">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="a93f1-137">Если вы заинтересованы в успешном или неисправном тесте, это может быть неважно.</span><span class="sxs-lookup"><span data-stu-id="a93f1-137">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="a93f1-138">Если вы хотите просмотреть все подробные сведения о возвращаемых данных, затем передаете выходные данные в командлет Format-List при выполнении теста:</span><span class="sxs-lookup"><span data-stu-id="a93f1-138">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="a93f1-139">Отобразятся выходные данные в более удобном формате для читателя:</span><span class="sxs-lookup"><span data-stu-id="a93f1-139">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="a93f1-140">Транслатеднумбер: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="a93f1-140">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="a93f1-141">Матчингруле: Description =; Pattern = ^ ( \\ d {11} ) $; Перевод = + $1;</span><span class="sxs-lookup"><span data-stu-id="a93f1-141">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="a93f1-142">Name = prefix ALL; Исинтерналекстенсион = false</span><span class="sxs-lookup"><span data-stu-id="a93f1-142">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="a93f1-143">Фирсматчинграуте: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="a93f1-143">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="a93f1-144">Матчингусаже: local</span><span class="sxs-lookup"><span data-stu-id="a93f1-144">MatchingUsage : Local</span></span>

<span data-ttu-id="a93f1-145">Если проверка завершилась ошибкой, Test-CsVoiceUser вернет пустой набор значений свойств:</span><span class="sxs-lookup"><span data-stu-id="a93f1-145">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="a93f1-146">Транслатеднумбер Матчингруле Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="a93f1-146">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="a93f1-147">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="a93f1-147">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a93f1-148">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="a93f1-148">Reasons why the test might have failed</span></span>

<span data-ttu-id="a93f1-149">Существует несколько причин, по которым может произойти ошибка командлета Test-CsVoiceUser: возможно, не существует правила нормализации, которое может перевести предоставленный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="a93f1-149">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="a93f1-150">Возможны проблемы с маршрутом голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="a93f1-150">There could be problems with the voice route.</span></span> <span data-ttu-id="a93f1-151">Может быть вызвана ошибка конфигурации абонентской группы, назначенной пользователю.</span><span class="sxs-lookup"><span data-stu-id="a93f1-151">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="a93f1-152">Поэтому при запуске командлета Test-CsVoiceUser может потребоваться включить параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="a93f1-152">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="a93f1-153">Если включен подробный командлет, Test-CsVoiceUser будет выдавать подробные сведения о всех действиях, выполняемых при проведении проверок.</span><span class="sxs-lookup"><span data-stu-id="a93f1-153">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="a93f1-154">Например, вы можете увидеть приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a93f1-154">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="a93f1-155">VERBOSE: Поиск пользователя с идентификатором "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="a93f1-155">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="a93f1-156">VERBOSE: Загрузка абонентской группы: "абонентскую redmonddialplan"</span><span class="sxs-lookup"><span data-stu-id="a93f1-156">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="a93f1-157">В этой дополнительной информации можно найти указания по выявлению причин сбоя.</span><span class="sxs-lookup"><span data-stu-id="a93f1-157">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="a93f1-158">Например, подробный вывод показывает, что тестируемому пользователю назначена абонентская схема абонентскую redmonddialplan.</span><span class="sxs-lookup"><span data-stu-id="a93f1-158">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="a93f1-159">Если тест завершился с ошибкой, следующим логическим шагом будет проверка того, что абонентскую redmonddialplan может перевести предоставленный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="a93f1-159">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a93f1-160">См. также</span><span class="sxs-lookup"><span data-stu-id="a93f1-160">See Also</span></span>


[<span data-ttu-id="a93f1-161">Test-Ксвоицеусер</span><span class="sxs-lookup"><span data-stu-id="a93f1-161">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

