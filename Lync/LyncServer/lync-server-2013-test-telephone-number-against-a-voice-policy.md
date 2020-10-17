---
title: 'Lync Server 2013: Проверка телефонного номера на соответствие политике голосовой связи'
description: 'Lync Server 2013: Проверка телефонного номера на соответствие политике голосовой связи.'
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
ms.openlocfilehash: 5a6523e7657bd4c30c23909bb02e2569b6067298
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548035"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="79c6d-103">Проверка телефонного номера на соответствие политике голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c6d-103">Test telephone number against a voice policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c6d-104">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="79c6d-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c6d-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="79c6d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="79c6d-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="79c6d-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6d-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="79c6d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="79c6d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79c6d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6d-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="79c6d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="79c6d-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="79c6d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="79c6d-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="79c6d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="79c6d-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="79c6d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="79c6d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="79c6d-113">Description</span></span>

<span data-ttu-id="79c6d-114">Способность пользователей корпоративной голосовой связи совершать исходящие телефонные звонки по каналам связи через телефонную сеть общего пользования (PSTN) по большей части на три вещи.</span><span class="sxs-lookup"><span data-stu-id="79c6d-114">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="79c6d-115">Политика голосовой связи, назначенная пользователю.</span><span class="sxs-lookup"><span data-stu-id="79c6d-115">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="79c6d-116">Маршруты голосовых вызовов, используемые для направления вызовов с сервера Lync Server в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="79c6d-116">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="79c6d-117">Использование PSTN, свойство Lync Server, которое подключает голосовую политику к маршруту голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="79c6d-117">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="79c6d-118">Особенно важна использование PSTN: это свойство, которое подключает голосовую политику к маршруту голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="79c6d-118">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="79c6d-119">(Политика голосовой связи и маршрут голосовой связи называются подключенными, если они имеют по крайней мере одну общую PSTN). Политики голосовой связи можно настроить без указания использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="79c6d-119">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="79c6d-120">В этом случае пользователи, которым назначена эта политика, не смогут совершать исходящие вызовы по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="79c6d-120">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="79c6d-121">Аналогично, маршруты голосовой связи, не имеющие по крайней мере одного указанного использования PSTN, не смогут маршрутизировать вызовы в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="79c6d-121">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="79c6d-122">Командлет Test-CsVoicePolicy проверяет, имеет ли указанная политика голосовой связи использование PSTN и используется ли по крайней мере один маршрут голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="79c6d-122">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="79c6d-123">В случае успешного выполнения проверки Test-CsVoicePolicy командлет сообщит имя первого действительного маршрута голосовых вызовов, а также имя использования PSTN, соединяющее политику с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="79c6d-123">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="79c6d-124">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="79c6d-124">Running the test</span></span>

<span data-ttu-id="79c6d-125">Для запуска командлета Test-CsVoicePolicy сначала необходимо использовать командлет Get-CsVoicePolicy, чтобы получить экземпляр политики голосовой связи, который необходимо протестировать; Затем этот экземпляр должен быть передан в командлет Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="79c6d-125">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="79c6d-126">Например:</span><span class="sxs-lookup"><span data-stu-id="79c6d-126">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="79c6d-127">Обратите внимание, что эта команда, которая не использует Get-CsVoicePolicy для получения экземпляра политики голосовой связи, не будет выполнена:</span><span class="sxs-lookup"><span data-stu-id="79c6d-127">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="79c6d-128">Если вы хотите проверить все политики голосовой связи по указанному номеру телефона, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="79c6d-128">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="79c6d-129">Обратите внимание, что Таржетнумбер необходимо указать с помощью формата E. 164.</span><span class="sxs-lookup"><span data-stu-id="79c6d-129">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="79c6d-130">Test-CsVoicePolicy не будет пытаться нормализовать или преобразовывать номера телефонов в формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="79c6d-130">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="79c6d-131">Для получения дополнительных сведений обратитесь к справочной документации по командлету Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="79c6d-131">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="79c6d-132">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="79c6d-132">Determining success or failure</span></span>

<span data-ttu-id="79c6d-133">Если политика голосовой связи может найти как совпадающий маршрут голосовой связи, так и соответствующее использование PSTN, на экране будет отображаться маршрут и использование:</span><span class="sxs-lookup"><span data-stu-id="79c6d-133">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="79c6d-134">Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="79c6d-134">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="79c6d-135">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="79c6d-135">\------------------ -------------</span></span>

<span data-ttu-id="79c6d-136">Редмондвоицерауте Редмондпстнусаже</span><span class="sxs-lookup"><span data-stu-id="79c6d-136">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="79c6d-137">Если не удается найти подходящий маршрут голосовой связи или подходящее использование PSTN, на экране будут отображаться пустые значения свойств.</span><span class="sxs-lookup"><span data-stu-id="79c6d-137">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="79c6d-138">Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="79c6d-138">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="79c6d-139">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="79c6d-139">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="79c6d-140">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="79c6d-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="79c6d-141">Если Test-CsVoicePolicy не возвращает соответствующее значение, которое может означать, что политика голосовой связи не обеспечивает совместное использование PSTN с маршрутом голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="79c6d-141">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="79c6d-142">Чтобы убедиться, что использование PSTN назначено политике голосовой связи, используйте командлет, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="79c6d-142">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="79c6d-143">Затем выполните следующую команду, чтобы определить использование PSTN, назначаемое каждому из ваших голосовых маршрутов:</span><span class="sxs-lookup"><span data-stu-id="79c6d-143">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="79c6d-144">Если отображаются совпадения (то есть, если вы видите один или несколько маршрутов голосовой связи, которые совместно используют по крайней мере одно использование PSTN с политикой голосовой связи), то следует запустить командлет Test-CsVoiceRoute, чтобы проверить, может ли маршрут голосом набирать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="79c6d-144">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79c6d-145">См. также</span><span class="sxs-lookup"><span data-stu-id="79c6d-145">See Also</span></span>


[<span data-ttu-id="79c6d-146">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="79c6d-146">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

