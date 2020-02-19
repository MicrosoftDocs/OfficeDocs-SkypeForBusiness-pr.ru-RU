---
title: 'Lync Server 2013: Проверка телефонного номера на соответствие политике голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7670e99fc7ac7688eff360a28be6f7280d6191b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="13215-102">Проверка телефонного номера на соответствие политике голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13215-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13215-103">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="13215-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13215-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="13215-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="13215-105">Monthly Channel</span><span class="sxs-lookup"><span data-stu-id="13215-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13215-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="13215-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="13215-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13215-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13215-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="13215-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="13215-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="13215-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="13215-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="13215-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="13215-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="13215-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="13215-112">Описание</span><span class="sxs-lookup"><span data-stu-id="13215-112">Description</span></span>

<span data-ttu-id="13215-113">Способность пользователей корпоративной голосовой связи совершать исходящие телефонные звонки по каналам связи через телефонную сеть общего пользования (PSTN) по большей части на три вещи.</span><span class="sxs-lookup"><span data-stu-id="13215-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="13215-114">Политика голосовой связи, назначенная пользователю.</span><span class="sxs-lookup"><span data-stu-id="13215-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="13215-115">Маршруты голосовых вызовов, используемые для направления вызовов с сервера Lync Server в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="13215-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="13215-116">Использование PSTN, свойство Lync Server, которое подключает голосовую политику к маршруту голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="13215-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="13215-117">Особенно важна использование PSTN: это свойство, которое подключает голосовую политику к маршруту голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="13215-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="13215-118">(Политика голосовой связи и маршрут голосовой связи называются подключенными, если они имеют по крайней мере одну общую PSTN). Политики голосовой связи можно настроить без указания использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="13215-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="13215-119">В этом случае пользователи, которым назначена эта политика, не смогут совершать исходящие вызовы по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="13215-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="13215-120">Аналогично, маршруты голосовой связи, не имеющие по крайней мере одного указанного использования PSTN, не смогут маршрутизировать вызовы в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="13215-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="13215-121">Командлет Test-CsVoicePolicy проверяет, имеет ли указанная политика голосовой связи использование PSTN и используется ли по крайней мере один маршрут голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="13215-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="13215-122">Если проверка выполняется с помощью командлета Test-CsVoicePolicy, командлет сообщит имя первого действительного маршрута голосовой связи, а также имя использования PSTN, соединяющее политику с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="13215-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="13215-123">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="13215-123">Running the test</span></span>

<span data-ttu-id="13215-124">Для запуска командлета Test-CsVoicePolicy сначала необходимо использовать командлет Get-CsVoicePolicy, чтобы извлечь экземпляр политики голосовой связи, который необходимо протестировать; Затем этот экземпляр должен быть передан в командлет Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="13215-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="13215-125">Например:</span><span class="sxs-lookup"><span data-stu-id="13215-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="13215-126">Обратите внимание, что эта команда, которая не использует командлет Get – CsVoicePolicy для получения экземпляра политики голосовой связи, не сможет выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="13215-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="13215-127">Если вы хотите проверить все политики голосовой связи по указанному номеру телефона, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="13215-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="13215-128">Обратите внимание, что Таржетнумбер необходимо указать с помощью формата E. 164.</span><span class="sxs-lookup"><span data-stu-id="13215-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="13215-129">Test-CsVoicePolicy не пытается нормализовать или преобразовывать номера телефонов в формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="13215-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="13215-130">Дополнительные сведения можно найти в справочной документации по командлету Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="13215-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="13215-131">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="13215-131">Determining success or failure</span></span>

<span data-ttu-id="13215-132">Если политика голосовой связи может найти как совпадающий маршрут голосовой связи, так и соответствующее использование PSTN, на экране будет отображаться маршрут и использование:</span><span class="sxs-lookup"><span data-stu-id="13215-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="13215-133">Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="13215-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="13215-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="13215-134">\------------------ -------------</span></span>

<span data-ttu-id="13215-135">Редмондвоицерауте Редмондпстнусаже</span><span class="sxs-lookup"><span data-stu-id="13215-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="13215-136">Если не удается найти подходящий маршрут голосовой связи или подходящее использование PSTN, на экране будут отображаться пустые значения свойств.</span><span class="sxs-lookup"><span data-stu-id="13215-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="13215-137">Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="13215-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="13215-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="13215-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="13215-139">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="13215-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="13215-140">Если Test-CsVoicePolicy не возвращает соответствующее значение, которое может означать, что политика голосовой связи не обеспечивает совместное использование PSTN с маршрутом голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="13215-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="13215-141">Чтобы убедиться, что использование PSTN назначено политике голосовой связи, используйте командлет, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="13215-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="13215-142">Затем выполните следующую команду, чтобы определить использование PSTN, назначаемое каждому из ваших голосовых маршрутов:</span><span class="sxs-lookup"><span data-stu-id="13215-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="13215-143">Если отображаются совпадения (то есть, если вы видите один или несколько маршрутов голосовой связи, которые совместно используют по крайней мере одно использование PSTN с политикой голосовой связи), необходимо запустить командлет Test-Ксвоицерауте, чтобы убедиться, что голосовой маршрут может набрать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="13215-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13215-144">См. также</span><span class="sxs-lookup"><span data-stu-id="13215-144">See Also</span></span>


[<span data-ttu-id="13215-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="13215-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

