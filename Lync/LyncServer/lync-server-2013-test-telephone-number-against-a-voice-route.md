---
title: 'Lync Server 2013: Проверка номера телефона на маршруте голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="6cf1a-102">Проверка номера телефона на маршруте голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cf1a-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cf1a-103">_**Тема последнего изменения:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="6cf1a-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cf1a-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="6cf1a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6cf1a-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="6cf1a-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf1a-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="6cf1a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6cf1a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cf1a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cf1a-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="6cf1a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6cf1a-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6cf1a-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксвоицерауте.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="6cf1a-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6cf1a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6cf1a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6cf1a-112">Description</span></span>

<span data-ttu-id="6cf1a-113">Голосовые маршруты работают вместе с голосовыми политиками, помогающие перенаправлять голосовые звонки в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="6cf1a-114">Каждый маршрут голосовой связи содержит регулярное выражение (шаблон номера), который определяет номера телефонов, которые будут маршрутизироваться по данному голосовому маршруту. маршрут сможет обрабатывать любые телефонные номера, соответствующие этому регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="6cf1a-115">Например, голосовой маршрут может иметь регулярное выражение, которое позволяет ему обрабатывать любое 10-значное число.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="6cf1a-116">Это означает, что маршрут сможет обработать номер телефона, например:</span><span class="sxs-lookup"><span data-stu-id="6cf1a-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="6cf1a-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="6cf1a-117">2065551219</span></span>

<span data-ttu-id="6cf1a-118">Маршрут не может обрабатывать одно из следующих двух чисел, оба из которых содержат 10 цифр:</span><span class="sxs-lookup"><span data-stu-id="6cf1a-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="6cf1a-119">5551219</span><span class="sxs-lookup"><span data-stu-id="6cf1a-119">5551219</span></span>

  - <span data-ttu-id="6cf1a-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="6cf1a-120">12065551219</span></span>

<span data-ttu-id="6cf1a-121">Командлет Test-Ксвоицерауте проверяет, может ли указанный голосовой маршрут перенаправлять указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6cf1a-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="6cf1a-122">Running the test</span></span>

<span data-ttu-id="6cf1a-123">Проверка возможности маршрута голоса к указанному номеру телефона состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="6cf1a-124">Сначала необходимо использовать командлет Get-Ксвоицерауте, чтобы вернуть экземпляр маршрута голосовой связи, а затем использовать командлет Test-Ксвоицерауте, чтобы проверить способность маршрута обрабатывать номер целевого телефона.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="6cf1a-125">Например, эта команда проверяет, может ли голосовой маршрут Редмондвоицерауте перенаправлять номер телефона 2065551219:</span><span class="sxs-lookup"><span data-stu-id="6cf1a-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="6cf1a-126">Обратите внимание на то, что номер телефона должен вводиться так, как ожидается, что пользователи будут набирать этот номер.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="6cf1a-127">Например, если вы не предполагаете, что пользователи должны включать код страны и города при наборе номера, используйте синтаксис, подобный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="6cf1a-128">В этом случае целевой номер выходит из кода страны и кода города.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="6cf1a-129">Чтобы использовать одну команду для проверки всех голосовых маршрутов по указанному целевому номеру, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6cf1a-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="6cf1a-130">Дополнительные сведения можно найти в справочной документации по командлету Test-Ксвоицерауте.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6cf1a-131">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="6cf1a-131">Determining success or failure</span></span>

<span data-ttu-id="6cf1a-132">Если маршрут голосовой связи может перенаправлять целевой номер телефона, командлет Test-Ксвоицерауте просто возвращает значение true:</span><span class="sxs-lookup"><span data-stu-id="6cf1a-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="6cf1a-133">Матчеспаттерн</span><span class="sxs-lookup"><span data-stu-id="6cf1a-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="6cf1a-134">True</span><span class="sxs-lookup"><span data-stu-id="6cf1a-134">True</span></span>

<span data-ttu-id="6cf1a-135">Это означает, что маршрут может обрабатывать номера, аналогичные целевому номеру.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="6cf1a-136">Если голосовой маршрут не может обработать целевой номер, функция Test-Ксвоицерауте возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="6cf1a-137">Матчеспаттерн</span><span class="sxs-lookup"><span data-stu-id="6cf1a-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="6cf1a-138">False</span><span class="sxs-lookup"><span data-stu-id="6cf1a-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6cf1a-139">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="6cf1a-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="6cf1a-140">При тестировании голосовых маршрутов "сбой" — это относительный термин.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="6cf1a-141">В этом случае это не означает, что маршрут является "разорванным"; вместо этого он просто означает, что маршрут не может обработать целевой номер.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="6cf1a-142">Это может быть вызвано неправильным настройкам голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="6cf1a-143">Это также может означать, что маршрут не предназначался для обработки чисел с помощью этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="6cf1a-144">Например, если вы не хотите перенаправлять звонки в другие страны по определенному маршруту, этот маршрут можно настроить таким образом, чтобы он отклонил все номера телефонов, включающие код страны.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="6cf1a-145">Если функция Test-Ксвоицерауте возвращает значение ложь, если предполагается, что она возвращает значение истина, убедитесь, что конечный номер введен правильно.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="6cf1a-146">Если вы сделали это, для просмотра Нумберпаттерн, настроенного для маршрута, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6cf1a-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6cf1a-147">См. также</span><span class="sxs-lookup"><span data-stu-id="6cf1a-147">See Also</span></span>


[<span data-ttu-id="6cf1a-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="6cf1a-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

