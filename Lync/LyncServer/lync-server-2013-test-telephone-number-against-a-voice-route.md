---
title: 'Lync Server 2013: Проверка телефонного номера на соответствие маршруту голосовой связи'
description: 'Lync Server 2013: тестовый номер телефона по маршруту голосовой связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789f4a538a992a72abf61f4c1fbdb98370f2e643
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563395"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="5fe1b-103">Проверка номера телефона на соответствие маршруту голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fe1b-103">Test telephone number against a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fe1b-104">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="5fe1b-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fe1b-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="5fe1b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5fe1b-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="5fe1b-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe1b-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="5fe1b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5fe1b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fe1b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fe1b-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5fe1b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5fe1b-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5fe1b-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="5fe1b-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5fe1b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5fe1b-113">Description</span></span>

<span data-ttu-id="5fe1b-114">Маршруты голосовой связи работают вместе с политиками голосовой связи для направления вызовов корпоративной голосовой связи в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-114">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="5fe1b-115">Каждый маршрут голосовой связи включает регулярное выражение (шаблон номера), которое определяет номера телефонов, которые будут маршрутизироваться через указанный маршрут голосовых вызовов: маршрут будет обрабатывать любые телефонные номера, которые удовлетворяют этому регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-115">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="5fe1b-116">Например, маршрут голосовой связи может иметь регулярное выражение, которое позволяет ему обрабатывать все 10 цифр.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-116">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="5fe1b-117">Это означает, что маршрут сможет обработать номер телефона, подобный указанному ниже.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-117">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="5fe1b-118">2065551219</span><span class="sxs-lookup"><span data-stu-id="5fe1b-118">2065551219</span></span>

<span data-ttu-id="5fe1b-119">Маршрут не сможет обработать один из следующих двух чисел, оба из которых не имеют 10 цифр:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-119">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="5fe1b-120">5551219</span><span class="sxs-lookup"><span data-stu-id="5fe1b-120">5551219</span></span>

  - <span data-ttu-id="5fe1b-121">12065551219</span><span class="sxs-lookup"><span data-stu-id="5fe1b-121">12065551219</span></span>

<span data-ttu-id="5fe1b-122">Командлет Test-CsVoiceRoute проверяет, может ли данный маршрут голосом маршрутизировать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-122">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5fe1b-123">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="5fe1b-123">Running the test</span></span>

<span data-ttu-id="5fe1b-124">Проверка возможности маршрута голосовых вызовов к указанному номеру телефона состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-124">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="5fe1b-125">Сначала необходимо использовать командлет Get-CsVoiceRoute, чтобы возвратить экземпляр маршрута голосовой связи, а затем использовать командлет Test-CsVoiceRoute, чтобы проверить способность этого маршрута обрабатывать целевой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-125">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="5fe1b-126">Например, эта команда проверяет, может ли маршрут голосовой связи Редмондвоицерауте маршрутизировать номер телефона 2065551219:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-126">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="5fe1b-127">Обратите внимание на то, что номер должен быть введен так, как предполагается, что пользователи набирает этот номер.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-127">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="5fe1b-128">Например, если вы не хотите, чтобы пользователи включали код страны и код города при наборе номера, используйте синтаксис, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-128">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="5fe1b-129">В этом случае целевой номер оставляет и код страны, и код города.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-129">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="5fe1b-130">Чтобы использовать одну команду для проверки всех маршрутов голосовой связи по указанному целевому номеру, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-130">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="5fe1b-131">Для получения дополнительных сведений обратитесь к справочной документации по командлету Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-131">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5fe1b-132">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="5fe1b-132">Determining success or failure</span></span>

<span data-ttu-id="5fe1b-133">Если маршрут голосовых вызовов может маршрутизировать целевой номер телефона, командлет Test-CsVoiceRoute просто возвращает значение true:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-133">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="5fe1b-134">матчеспаттерн</span><span class="sxs-lookup"><span data-stu-id="5fe1b-134">MatchesPattern</span></span>

\--------------

<span data-ttu-id="5fe1b-135">Верно</span><span class="sxs-lookup"><span data-stu-id="5fe1b-135">True</span></span>

<span data-ttu-id="5fe1b-136">Это означает, что маршрут может обрабатывать числа, аналогичные целевому номеру.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-136">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="5fe1b-137">Если маршрут голосовых вызовов не может обработать целевой номер, Test-CsVoiceRoute возвращает значение false:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-137">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="5fe1b-138">матчеспаттерн</span><span class="sxs-lookup"><span data-stu-id="5fe1b-138">MatchesPattern</span></span>

\--------------

<span data-ttu-id="5fe1b-139">False</span><span class="sxs-lookup"><span data-stu-id="5fe1b-139">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5fe1b-140">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="5fe1b-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="5fe1b-141">При тестировании голосовых маршрутов "сбой" является относительным термином.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-141">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="5fe1b-142">В этом случае это не означает, что маршрут является каким-либо «сломанным», а просто только означает, что маршрут не может обработать целевой номер.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-142">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="5fe1b-143">Это может быть вызвано неправильной настройкой маршрута голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-143">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="5fe1b-144">Это также может означать, что маршрут не предназначен для обработки чисел с помощью этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-144">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="5fe1b-145">Например, если вы не хотите маршрутизировать звонки в другие страны по указанному маршруту, можно настроить отклонения всех номеров телефонов, включающих код страны, в другие страны.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-145">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="5fe1b-146">Если Test-CsVoiceRoute возвращает значение false, если ожидается, что возвращаемое значение равно true, убедитесь, что целевой номер введен правильно.</span><span class="sxs-lookup"><span data-stu-id="5fe1b-146">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="5fe1b-147">В этом случае используйте команду, аналогичную следующей, для просмотра Нумберпаттерн, настроенной для маршрута:</span><span class="sxs-lookup"><span data-stu-id="5fe1b-147">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fe1b-148">См. также</span><span class="sxs-lookup"><span data-stu-id="5fe1b-148">See Also</span></span>


[<span data-ttu-id="5fe1b-149">Test-Ксвоицерауте</span><span class="sxs-lookup"><span data-stu-id="5fe1b-149">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

