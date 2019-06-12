---
title: 'Lync Server 2013: Проверка конфигурации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="97116-102">Проверка конфигурации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97116-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97116-103">_**Тема последнего изменения:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="97116-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97116-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="97116-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="97116-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="97116-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97116-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="97116-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="97116-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="97116-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97116-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="97116-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="97116-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="97116-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="97116-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксвоицетестконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="97116-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="97116-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="97116-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="97116-112">Описание</span><span class="sxs-lookup"><span data-stu-id="97116-112">Description</span></span>

<span data-ttu-id="97116-113">Lync Server включает несколько командлетов Windows PowerShell (например, Test-Ксвоицерауте и Test-Ксвоицеполици, Test-CsTrunkConfiguration), которые позволяют удостовериться, что отдельные части корпоративной голосовой инфраструктуры – маршруты голосовой связи, голосовые сообщения политики, магистральные магистрали SIP – работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="97116-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="97116-114">Несмотря на то, что в корпоративной голосовой связи все индивидуальные компоненты работают, вы можете использовать допустимый голосовой маршрут, действительную голосовую политику и действительную магистраль SIP, но при этом пользователи не смогут совершать и принимать телефонные звонки.</span><span class="sxs-lookup"><span data-stu-id="97116-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="97116-115">По этой причине Lync Server также предоставляет возможность создавать конфигурации тестовых тестов.</span><span class="sxs-lookup"><span data-stu-id="97116-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="97116-116">Конфигурации тестовых тестов — это распространенные сценарии для корпоративных клиентов: вы можете указать такие параметры, как голосовая связь, политика голосовой связи и абонентская группа, а затем убедиться, что эти индивидуальные элементы смогут работать вместе для предоставления услуг телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="97116-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="97116-117">Кроме того, вы можете проверить свои ожидания в указанном сценарии.</span><span class="sxs-lookup"><span data-stu-id="97116-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="97116-118">Например, предположим, что сочетание абонентов и политик голосовой связи "B" привело бы к переадресации звонков по голосовой маршруту C. Вы можете ввести голосовой маршрут C в качестве Експектедрауте.</span><span class="sxs-lookup"><span data-stu-id="97116-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="97116-119">Если при выполнении теста маршрут "C" не установлен, проверка будет помечена как невыполненная.</span><span class="sxs-lookup"><span data-stu-id="97116-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="97116-120">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="97116-120">Running the test</span></span>

<span data-ttu-id="97116-121">Перед тестированием коллекций голосовой конфигурации с помощью Windows PowerShell необходимо сначала использовать командлет Get-Ксвоицетестконфигуратион для получения экземпляра этих параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="97116-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="97116-122">Затем этот экземпляр должен быть передан в тест-Ксвоицетестконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="97116-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="97116-123">Например:</span><span class="sxs-lookup"><span data-stu-id="97116-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="97116-124">Для одновременной проверки всех параметров конфигурации голосового теста используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="97116-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="97116-125">Дополнительные сведения можно найти в справочной документации по командлету Test-Ксвоицетестконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="97116-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="97116-126">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="97116-126">Determining success or failure</span></span>

<span data-ttu-id="97116-127">Командлет Test-Ксвоицетестконфигуратион сообщает о том, что тест завершился сбоем или успешно, и предоставляет дополнительные сведения о каждом успешном прохождении теста, такие как правило трансляции, маршрут голосовой связи и использование PSTN, используемое для выполнения задачи:</span><span class="sxs-lookup"><span data-stu-id="97116-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="97116-128">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="97116-128">Result:             Success</span></span>

<span data-ttu-id="97116-129">Транслатеднумбер: + 15551234</span><span class="sxs-lookup"><span data-stu-id="97116-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="97116-130">Матчингруле: описание =; Шаблон = ^ (\\d{4}) $; Перевод = + 1\\d; Name = Test; Исинтерналекстенсион = false</span><span class="sxs-lookup"><span data-stu-id="97116-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="97116-131">Фирстматчинграуте: сайт: Redmond</span><span class="sxs-lookup"><span data-stu-id="97116-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="97116-132">Матчингусаже: local</span><span class="sxs-lookup"><span data-stu-id="97116-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="97116-133">Если тест не удалось выполнить, результат будет указан как ошибка.</span><span class="sxs-lookup"><span data-stu-id="97116-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="97116-134">Результат: Failed</span><span class="sxs-lookup"><span data-stu-id="97116-134">Result:             Fail</span></span>

<span data-ttu-id="97116-135">Транслатеднумбер:</span><span class="sxs-lookup"><span data-stu-id="97116-135">TranslatedNumber:</span></span>   

<span data-ttu-id="97116-136">Фирстматчинграуте:</span><span class="sxs-lookup"><span data-stu-id="97116-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="97116-137">Матчингусаже:</span><span class="sxs-lookup"><span data-stu-id="97116-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="97116-138">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="97116-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="97116-139">Поскольку тестирование конфигурации для проверки правописания проверяет несколько различных элементов, в том числе политики голосовой связи, абонентские группы, маршруты голосовой почты и т. д., это может привести к неудачному тесту.</span><span class="sxs-lookup"><span data-stu-id="97116-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="97116-140">Если тест завершается сбоем, первым шагом необходимо проверить параметры конфигурации с помощью командлета Get-Ксвоицетестконфигуратион:</span><span class="sxs-lookup"><span data-stu-id="97116-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="97116-141">Если параметры настроены правильно, повторно выполните тест, включив параметр Verbose.</span><span class="sxs-lookup"><span data-stu-id="97116-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="97116-142">Параметр verbose предоставит пошаговые инструкции для каждого действия, выполненного с помощью теста-Ксвоицетестконфигуратион, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="97116-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="97116-143">ПОДРОБНЫй: Загрузка абонентской группы: "Global"</span><span class="sxs-lookup"><span data-stu-id="97116-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="97116-144">ПОДРОБНЫй: Загрузка политики голосовой связи: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="97116-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="97116-145">Эта пошаговая учетная запись может быть полезна в том случае, если тест действительно завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="97116-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="97116-146">В противном случае вы можете использовать другие командлеты Windows PowerShell (например, Test-Ксвоицеполици) и месодикалли Begin для проверки отдельных компонентов, которые включены в параметры конфигурации голосового теста.</span><span class="sxs-lookup"><span data-stu-id="97116-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="97116-147">Кроме того, обратите внимание на то, что тест может перенаправлять вызов, но все еще не помечается как сбой. Это может произойти, если вы ввели значения для Експектедрауте, Експектедтранслатеднумбер и Експектедусаже, и любые из этих ожиданий не будут удовлетворены.</span><span class="sxs-lookup"><span data-stu-id="97116-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="97116-148">Например, предположим, что вы ввели голосовую переадресацию в качестве ожидаемого голоса, но проверка завершит звонок с помощью голосового маршрута г. В этом случае тест будет помечен как сбой, так как ожидаемый маршрут голосовой связи не использовался.</span><span class="sxs-lookup"><span data-stu-id="97116-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="97116-149">Если тест завершается сбоем, вы можете удалить значения для Експектедрауте, Експектедтранслатеднумбер и Експектедусаже, а затем повторно выполнить тест.</span><span class="sxs-lookup"><span data-stu-id="97116-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="97116-150">Это поможет вам определить, завершился ли сбой из-за того, что не удалось выполнить звонок или вы ожидаете одного и фактического получения другого.</span><span class="sxs-lookup"><span data-stu-id="97116-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97116-151">См. также</span><span class="sxs-lookup"><span data-stu-id="97116-151">See Also</span></span>


[<span data-ttu-id="97116-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="97116-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

