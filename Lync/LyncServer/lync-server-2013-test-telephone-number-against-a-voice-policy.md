---
title: 'Lync Server 2013: Проверка номера телефона на соответствие политике голосовой связи'
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
ms.openlocfilehash: 37d0c9ae6512cb7755c7ef73e4cfd3e37b92884d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="674cd-102">Проверка номера телефона в соответствии с политикой голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="674cd-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="674cd-103">_**Тема последнего изменения:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="674cd-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="674cd-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="674cd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="674cd-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="674cd-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="674cd-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="674cd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="674cd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="674cd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="674cd-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="674cd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="674cd-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="674cd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="674cd-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксвоицеполици.</span><span class="sxs-lookup"><span data-stu-id="674cd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="674cd-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="674cd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="674cd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="674cd-112">Description</span></span>

<span data-ttu-id="674cd-113">Возможность пользователей корпоративной голосовой связи в отношении исходящих звонков по коммутируемой телефонной сети общего пользования (КТСОП) в крупных компонентах, как и в случае с тремя факторами:</span><span class="sxs-lookup"><span data-stu-id="674cd-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="674cd-114">Политика голосовой связи, назначенная пользователю.</span><span class="sxs-lookup"><span data-stu-id="674cd-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="674cd-115">Голосовые маршруты, используемые для направления звонков с сервера Lync Server в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="674cd-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="674cd-116">Использование КТСОП — свойство Lync Server, которое подключает голосовую политику к голосовому маршруту.</span><span class="sxs-lookup"><span data-stu-id="674cd-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="674cd-117">Особенно важна использование PSTN: это свойство, которое подключает голосовую политику к голосовому маршруту.</span><span class="sxs-lookup"><span data-stu-id="674cd-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="674cd-118">(Политика голосовой связи и голосовой маршрут говорят, что они будут подключены, если у них есть хотя бы одно общее использование PSTN.) Политики голосовой связи можно настроить, не задавая использование КТСОП.</span><span class="sxs-lookup"><span data-stu-id="674cd-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="674cd-119">В этом случае пользователи, которым назначена политика, не смогут совершать исходящие звонки через сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="674cd-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="674cd-120">Кроме того, маршруты голосовой связи, у которых нет хотя бы одного заданного использования PSTN, не смогут маршрутизировать звонки в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="674cd-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="674cd-121">Командлет Test-Ксвоицеполици удостоверяется в том, что данная политика голосовой связи использует PSTN и что она используется по крайней мере одним маршрутом голоса.</span><span class="sxs-lookup"><span data-stu-id="674cd-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="674cd-122">Если проверка выполняется с помощью теста-Ксвоицеполици, командлет сообщит имя первого действительного маршрута голосовой связи, а также имя использования КТСОП, соединяющее политику с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="674cd-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="674cd-123">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="674cd-123">Running the test</span></span>

<span data-ttu-id="674cd-124">Чтобы запустить командлет Test-Ксвоицеполици, необходимо сначала использовать командлет Get-Ксвоицеполици, чтобы получить экземпляр политики голосовой связи, которую нужно проверить; Этот экземпляр затем должен быть передан в Test-Ксвоицеполици.</span><span class="sxs-lookup"><span data-stu-id="674cd-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="674cd-125">Например:</span><span class="sxs-lookup"><span data-stu-id="674cd-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="674cd-126">Обратите внимание, что эта команда, которая не использует Get-Ксвоицеполици для получения экземпляра политики голосовой связи, не может выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="674cd-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="674cd-127">Если вы хотите проверить все политики голосовой связи по указанному номеру телефона, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="674cd-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="674cd-128">Обратите внимание, что Таржетнумбер необходимо указать с помощью формата E. 164.</span><span class="sxs-lookup"><span data-stu-id="674cd-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="674cd-129">Test-Ксвоицеполици не попытается выполнить нормализацию или перевод телефонных номеров в формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="674cd-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="674cd-130">Дополнительные сведения можно найти в справочной документации по командлету Test-Ксвоицеполици.</span><span class="sxs-lookup"><span data-stu-id="674cd-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="674cd-131">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="674cd-131">Determining success or failure</span></span>

<span data-ttu-id="674cd-132">Если политика голосовой связи может найти совпадающий маршрут голосовой связи и использование PSTN, то на экране будут отображаться как маршрут, так и использование.</span><span class="sxs-lookup"><span data-stu-id="674cd-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="674cd-133">Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="674cd-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="674cd-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="674cd-134">\------------------ -------------</span></span>

<span data-ttu-id="674cd-135">Редмондвоицерауте Редмондпстнусаже</span><span class="sxs-lookup"><span data-stu-id="674cd-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="674cd-136">Если не удается найти подходящий голосовой маршрут или подходящее использование КТСОП, на экране будут показаны пустые значения свойств.</span><span class="sxs-lookup"><span data-stu-id="674cd-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="674cd-137">Фирстматчинграуте Матчингусаже</span><span class="sxs-lookup"><span data-stu-id="674cd-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="674cd-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="674cd-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="674cd-139">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="674cd-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="674cd-140">Если "Test-Ксвоицеполици" не возвращает соответствие, которое может означать, что политика голосовой связи не использует PSTN с голосовым маршрутом.</span><span class="sxs-lookup"><span data-stu-id="674cd-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="674cd-141">Для проверки использования PSTN, назначенной политике голосовой связи, используйте командлет, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="674cd-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="674cd-142">Затем выполните эту команду, чтобы определить использование PSTN, назначаемое каждому из ваших голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="674cd-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="674cd-143">Если вы видите все совпадения (то есть, если вы видите один или несколько маршрутов голосовой связи, использующих по крайней мере одно использование PSTN с помощью голосовой политики), вы должны запустить командлет Test-Ксвоицерауте, чтобы убедиться, что голосовой маршрут сможет набрать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="674cd-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="674cd-144">См. также</span><span class="sxs-lookup"><span data-stu-id="674cd-144">See Also</span></span>


[<span data-ttu-id="674cd-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="674cd-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

