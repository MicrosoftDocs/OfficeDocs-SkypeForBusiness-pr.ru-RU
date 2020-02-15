---
title: 'Lync Server 2013: Тестовая конфигурация голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2894d61a4dabd174315e24a225392bde7a893300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="3970f-102">Тестовая конфигурация голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3970f-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3970f-103">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="3970f-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3970f-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="3970f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3970f-105">Monthly Channel</span><span class="sxs-lookup"><span data-stu-id="3970f-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3970f-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="3970f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3970f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3970f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3970f-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="3970f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3970f-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3970f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3970f-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3970f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="3970f-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3970f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3970f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3970f-112">Description</span></span>

<span data-ttu-id="3970f-113">Lync Server включает несколько командлетов Windows PowerShell (например, Test-Ксвоицерауте и Test-CsVoicePolicy, Test-CsTrunkConfiguration), которые позволяют проверить, что отдельные части корпоративной голосовой связи — маршруты голосовых вызовов, голосовая связь политики, магистральные линии SIP — работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="3970f-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="3970f-114">Несмотря на то, что корпоративная голосовая связь важна для всех отдельных частей, может существовать действительный маршрут голосовых вызовов, действительная политика голосовой связи и действительная магистральная линия SIP, но пользователи не могут совершать или принимать телефонные звонки.</span><span class="sxs-lookup"><span data-stu-id="3970f-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="3970f-115">Из-за этого Lync Server также предоставляет возможность создавать конфигурации тестовых голосов.</span><span class="sxs-lookup"><span data-stu-id="3970f-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="3970f-116">Конфигурации тестовых тестов представляют собой распространенные сценарии корпоративной голосовой связи: вы можете указать такие параметры, как маршрут голосовой связи, политика голосовой связи и абонентская абонентская группы, а затем убедиться, что эти отдельные элементы могут работать совместно для предоставления услуг телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="3970f-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="3970f-117">Кроме того, вы можете проверить свои ожидания в определенном сценарии.</span><span class="sxs-lookup"><span data-stu-id="3970f-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="3970f-118">Например, предположим, что сочетание абонентской группы а и политика голосовой связи б приведут к маршрутизации вызовов через голосовую маршрутизацию C. Вы можете ввести Voice Route C в качестве Експектедрауте.</span><span class="sxs-lookup"><span data-stu-id="3970f-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="3970f-119">Если вы выполняете тест, если голосовая связь C не установлена, тест будет помечен как неудачный.</span><span class="sxs-lookup"><span data-stu-id="3970f-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3970f-120">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="3970f-120">Running the test</span></span>

<span data-ttu-id="3970f-121">Перед тестированием коллекций настройки голосовой связи с помощью Windows PowerShell сначала необходимо использовать командлет Get – CsVoiceTestConfiguration для получения экземпляра этих параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3970f-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="3970f-122">Затем этот экземпляр должен быть передан в командлет Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3970f-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="3970f-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="3970f-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="3970f-124">Чтобы проверить все параметры конфигурации проверки речи одновременно, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3970f-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="3970f-125">Дополнительные сведения можно найти в справочной документации по командлету Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3970f-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3970f-126">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="3970f-126">Determining success or failure</span></span>

<span data-ttu-id="3970f-127">Командлет Test-CsVoiceTestConfiguration сообщает о том, что тест завершился успешно или успешно, и предоставляет дополнительные сведения о каждом успешном тесте, такие как правило преобразования, маршрут голосовых вызовов и использование PSTN, используемое для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="3970f-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="3970f-128">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="3970f-128">Result:             Success</span></span>

<span data-ttu-id="3970f-129">Транслатеднумбер: + 15551234</span><span class="sxs-lookup"><span data-stu-id="3970f-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="3970f-130">Матчингруле: Description =; Pattern = ^ (\\d{4}) $; Перевод = + 1\\d; Name = Test; Исинтерналекстенсион = false</span><span class="sxs-lookup"><span data-stu-id="3970f-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="3970f-131">Фирстматчинграуте: site: Redmond</span><span class="sxs-lookup"><span data-stu-id="3970f-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="3970f-132">Матчингусаже: local</span><span class="sxs-lookup"><span data-stu-id="3970f-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="3970f-133">Если тест завершается неудачей, возвращается сообщение о сбое.</span><span class="sxs-lookup"><span data-stu-id="3970f-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="3970f-134">Результат: Failed</span><span class="sxs-lookup"><span data-stu-id="3970f-134">Result:             Fail</span></span>

<span data-ttu-id="3970f-135">Транслатеднумбер:</span><span class="sxs-lookup"><span data-stu-id="3970f-135">TranslatedNumber:</span></span>   

<span data-ttu-id="3970f-136">Фирстматчинграуте:</span><span class="sxs-lookup"><span data-stu-id="3970f-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="3970f-137">Матчингусаже:</span><span class="sxs-lookup"><span data-stu-id="3970f-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3970f-138">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="3970f-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="3970f-139">Так как тестовая конфигурация тестовой голосовой связи тестирует несколько различных элементов, в том числе политики голосовой связи, абонентские группы, маршруты голосовых вызовов и т. д., существует несколько различных факторов, которые могут привести к неудачному тестированию.</span><span class="sxs-lookup"><span data-stu-id="3970f-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="3970f-140">Если тест завершается неудачей, сначала необходимо проанализировать параметры конфигурации с помощью командлета Get-CsVoiceTestConfiguration:</span><span class="sxs-lookup"><span data-stu-id="3970f-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="3970f-141">Если параметры настроены правильно, повторно запустите тест, включив параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="3970f-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="3970f-142">Параметр verbose предоставляет пошаговые инструкции для каждого действия, выполняемого с помощью Test-CsVoiceTestConfiguration, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3970f-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="3970f-143">VERBOSE: Загрузка абонентской группы: "Глобальная"</span><span class="sxs-lookup"><span data-stu-id="3970f-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="3970f-144">VERBOSE: Загрузка политики голосовой связи: "абонентскую redmonddialplan"</span><span class="sxs-lookup"><span data-stu-id="3970f-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="3970f-145">Эта пошаговая учетная запись может быть полезной, если тест фактически не пройден.</span><span class="sxs-lookup"><span data-stu-id="3970f-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="3970f-146">В противном случае вы можете использовать другие командлеты Windows PowerShell (например, Test-CsVoicePolicy) и месодикалли начать проверку отдельных компонентов, включенных в параметры конфигурации теста голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3970f-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="3970f-147">Кроме того, следует учитывать, что можно проверить возможность маршрутизации вызова и все еще отмечена как ошибка; Это может произойти, если вы вводите значения для Експектедрауте, Експектедтранслатеднумбер и Експектедусаже, а все эти ожидания не выполняются.</span><span class="sxs-lookup"><span data-stu-id="3970f-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="3970f-148">Например, предположим, что в качестве ожидаемого маршрута голосового голоса указан голосовый маршрут C, но тест фактически завершает вызов с помощью маршрута голосовой связи D. В этом случае тест будет помечен как неудачный, так как ожидаемый маршрут голосовой связи не использовался.</span><span class="sxs-lookup"><span data-stu-id="3970f-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="3970f-149">Если тест завершается неудачей, можно удалить значения для Експектедрауте, Експектедтранслатеднумбер и Експектедусаже, а затем повторно выполнить тест.</span><span class="sxs-lookup"><span data-stu-id="3970f-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="3970f-150">Это поможет определить, вызвана ли ошибка из-за того, что не удалось выполнить звонок или вы ожидаете одного и действительного получения другого.</span><span class="sxs-lookup"><span data-stu-id="3970f-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3970f-151">См. также</span><span class="sxs-lookup"><span data-stu-id="3970f-151">See Also</span></span>


[<span data-ttu-id="3970f-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="3970f-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

