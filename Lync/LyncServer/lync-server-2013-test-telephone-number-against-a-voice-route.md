---
title: 'Lync Server 2013: Проверка телефонного номера на соответствие маршруту голосовой связи'
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
ms.openlocfilehash: 3fccdcb5dfc0fe52c2c0dcf80f7f6a374e35a39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="0e93c-102">Проверка номера телефона на соответствие маршруту голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e93c-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e93c-103">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="0e93c-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e93c-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="0e93c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0e93c-105">Monthly Channel</span><span class="sxs-lookup"><span data-stu-id="0e93c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e93c-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="0e93c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0e93c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e93c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e93c-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="0e93c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0e93c-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0e93c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0e93c-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксвоицерауте.</span><span class="sxs-lookup"><span data-stu-id="0e93c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="0e93c-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0e93c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0e93c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0e93c-112">Description</span></span>

<span data-ttu-id="0e93c-113">Маршруты голосовой связи работают вместе с политиками голосовой связи для направления вызовов корпоративной голосовой связи в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="0e93c-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="0e93c-114">Каждый маршрут голосовой связи включает регулярное выражение (шаблон номера), которое определяет номера телефонов, которые будут маршрутизироваться через указанный маршрут голосовых вызовов: маршрут будет обрабатывать любые телефонные номера, которые удовлетворяют этому регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="0e93c-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="0e93c-115">Например, маршрут голосовой связи может иметь регулярное выражение, которое позволяет ему обрабатывать все 10 цифр.</span><span class="sxs-lookup"><span data-stu-id="0e93c-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="0e93c-116">Это означает, что маршрут сможет обработать номер телефона, подобный указанному ниже.</span><span class="sxs-lookup"><span data-stu-id="0e93c-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="0e93c-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="0e93c-117">2065551219</span></span>

<span data-ttu-id="0e93c-118">Маршрут не сможет обработать один из следующих двух чисел, оба из которых не имеют 10 цифр:</span><span class="sxs-lookup"><span data-stu-id="0e93c-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="0e93c-119">5551219</span><span class="sxs-lookup"><span data-stu-id="0e93c-119">5551219</span></span>

  - <span data-ttu-id="0e93c-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="0e93c-120">12065551219</span></span>

<span data-ttu-id="0e93c-121">Командлет Test-Ксвоицерауте проверяет, может ли данный маршрут голосовой связи маршрутизировать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="0e93c-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0e93c-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="0e93c-122">Running the test</span></span>

<span data-ttu-id="0e93c-123">Проверка возможности маршрута голосовых вызовов к указанному номеру телефона состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="0e93c-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="0e93c-124">Сначала необходимо использовать командлет Get-Ксвоицерауте, чтобы возвратить экземпляр маршрута голосовой связи, а затем использовать командлет Test-Ксвоицерауте, чтобы проверить способность этого маршрута обрабатывать целевой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="0e93c-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="0e93c-125">Например, эта команда проверяет, может ли маршрут голосовой связи Редмондвоицерауте маршрутизировать номер телефона 2065551219:</span><span class="sxs-lookup"><span data-stu-id="0e93c-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="0e93c-126">Обратите внимание на то, что номер должен быть введен так, как предполагается, что пользователи набирает этот номер.</span><span class="sxs-lookup"><span data-stu-id="0e93c-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="0e93c-127">Например, если вы не хотите, чтобы пользователи включали код страны и код города при наборе номера, используйте синтаксис, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="0e93c-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="0e93c-128">В этом случае целевой номер оставляет и код страны, и код города.</span><span class="sxs-lookup"><span data-stu-id="0e93c-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="0e93c-129">Чтобы использовать одну команду для проверки всех маршрутов голосовой связи по указанному целевому номеру, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0e93c-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="0e93c-130">Дополнительные сведения можно найти в справочной документации по командлету Test-Ксвоицерауте.</span><span class="sxs-lookup"><span data-stu-id="0e93c-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0e93c-131">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="0e93c-131">Determining success or failure</span></span>

<span data-ttu-id="0e93c-132">Если маршрут голосовых вызовов может маршрутизировать целевой номер телефона, командлет Test-Ксвоицерауте просто возвращает значение true:</span><span class="sxs-lookup"><span data-stu-id="0e93c-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="0e93c-133">матчеспаттерн</span><span class="sxs-lookup"><span data-stu-id="0e93c-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="0e93c-134">Верно</span><span class="sxs-lookup"><span data-stu-id="0e93c-134">True</span></span>

<span data-ttu-id="0e93c-135">Это означает, что маршрут может обрабатывать числа, аналогичные целевому номеру.</span><span class="sxs-lookup"><span data-stu-id="0e93c-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="0e93c-136">Если маршрут голосовых вызовов не может обработать целевой номер, Test-Ксвоицерауте возвращает значение false:</span><span class="sxs-lookup"><span data-stu-id="0e93c-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="0e93c-137">матчеспаттерн</span><span class="sxs-lookup"><span data-stu-id="0e93c-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="0e93c-138">False</span><span class="sxs-lookup"><span data-stu-id="0e93c-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0e93c-139">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="0e93c-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="0e93c-140">При тестировании голосовых маршрутов "сбой" является относительным термином.</span><span class="sxs-lookup"><span data-stu-id="0e93c-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="0e93c-141">В этом случае это не означает, что маршрут является каким-либо «сломанным», а просто только означает, что маршрут не может обработать целевой номер.</span><span class="sxs-lookup"><span data-stu-id="0e93c-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="0e93c-142">Это может быть вызвано неправильной настройкой маршрута голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="0e93c-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="0e93c-143">Это также может означать, что маршрут не предназначен для обработки чисел с помощью этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="0e93c-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="0e93c-144">Например, если вы не хотите маршрутизировать звонки в другие страны по указанному маршруту, можно настроить отклонения всех номеров телефонов, включающих код страны, в другие страны.</span><span class="sxs-lookup"><span data-stu-id="0e93c-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="0e93c-145">Если Test-Ксвоицерауте возвращает значение false, если ожидается, что возвращаемое значение равно true, убедитесь, что целевой номер введен правильно.</span><span class="sxs-lookup"><span data-stu-id="0e93c-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="0e93c-146">В этом случае используйте команду, аналогичную следующей, для просмотра Нумберпаттерн, настроенной для маршрута:</span><span class="sxs-lookup"><span data-stu-id="0e93c-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e93c-147">См. также</span><span class="sxs-lookup"><span data-stu-id="0e93c-147">See Also</span></span>


[<span data-ttu-id="0e93c-148">Test-Ксвоицерауте</span><span class="sxs-lookup"><span data-stu-id="0e93c-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

