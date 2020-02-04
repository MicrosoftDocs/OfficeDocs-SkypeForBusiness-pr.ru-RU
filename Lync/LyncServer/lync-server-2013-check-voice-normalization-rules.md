---
title: 'Lync Server 2013: Проверка правил нормализации голосовых сообщений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04e383f38d5af6f106354a766c857635bcd87eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="0814a-102">Проверка правил нормализации голосовых сообщений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0814a-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0814a-103">_**Тема последнего изменения:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="0814a-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0814a-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="0814a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0814a-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="0814a-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0814a-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="0814a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0814a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0814a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0814a-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="0814a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0814a-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="0814a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0814a-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксвоиценормализатионруле.</span><span class="sxs-lookup"><span data-stu-id="0814a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="0814a-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0814a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0814a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0814a-112">Description</span></span>

<span data-ttu-id="0814a-113">Правила нормализации голоса используются для преобразования номера телефона, набранного пользователем (например, 2065551219), в формат E. 164, который используется приложением Lync Server (+ 12065551219).</span><span class="sxs-lookup"><span data-stu-id="0814a-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="0814a-114">Например, если пользователи находятся в привычке набрать номер телефона, не включая код страны или код города (например, 5551219), необходимо иметь правило нормализации голоса, которое может преобразовать этот номер в формат E. 164: + 12065551219.</span><span class="sxs-lookup"><span data-stu-id="0814a-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="0814a-115">Без такого правила пользователь не сможет позвонить в 555-1219.</span><span class="sxs-lookup"><span data-stu-id="0814a-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="0814a-116">Командлет Test-Ксвоиценормализатионруле удостоверяется в том, что указанное правило нормализации голоса может успешно преобразовать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="0814a-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="0814a-117">Например, эта команда проверяет, может ли глобальная Ноареакоде правило нормализации нормализация и преобразование строки набора 5551219.</span><span class="sxs-lookup"><span data-stu-id="0814a-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0814a-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="0814a-118">Running the test</span></span>

<span data-ttu-id="0814a-119">Чтобы запустить командлет Test-Ксвоиценормализатионруле, необходимо сначала использовать командлет Get-Ксвоиценормализатионруле, чтобы получить экземпляр тестируемого правила, а затем передать этот экземпляр для проверки в Ксвоиценормализатионруле.</span><span class="sxs-lookup"><span data-stu-id="0814a-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="0814a-120">Синтаксис, похожий на этот, не подходит.</span><span class="sxs-lookup"><span data-stu-id="0814a-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="0814a-121">Test-Ксвоиценормализатионруле-Диаледнумбер "12065551219" — Нормализатионруле "Global/prefix ALL"</span><span class="sxs-lookup"><span data-stu-id="0814a-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="0814a-122">Вместо этого используйте следующий синтаксис, объединяющий командлеты Get-Ксвоиценормализатионруле и Test-Ксвоиценормализатионруле:</span><span class="sxs-lookup"><span data-stu-id="0814a-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="0814a-123">Get-Ксвоиценормализатионруле-Identity "Global/prefix ALL" | Test-Ксвоиценормализатионруле-Диаледнумбер "12065551219"</span><span class="sxs-lookup"><span data-stu-id="0814a-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0814a-124">.</span><span class="sxs-lookup"><span data-stu-id="0814a-124">.</span></span> <span data-ttu-id="0814a-125">Кроме того, вы также можете использовать этот подход, чтобы получить экземпляр правила, а затем проверить правило по указанному номеру телефона.</span><span class="sxs-lookup"><span data-stu-id="0814a-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="0814a-126">Введите значение параметра Диаледнумбер точно так же, как ожидается набор номера.</span><span class="sxs-lookup"><span data-stu-id="0814a-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="0814a-127">Например, если указанное правило нормализации голоса должно автоматически добавлять код страны (первый 1 в значении 12065551219), то вы должны выйти из кода страны.</span><span class="sxs-lookup"><span data-stu-id="0814a-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="0814a-128">Если правило настроено правильно, оно автоматически добавляет код страны при переводе номера в формат E. 164, который используется в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0814a-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="0814a-129">Дополнительные сведения можно найти в справочной документации по командлету Test-Ксвоиценормализатионруле.</span><span class="sxs-lookup"><span data-stu-id="0814a-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0814a-130">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="0814a-130">Determining success or failure</span></span>

<span data-ttu-id="0814a-131">Если указанное правило нормализации голоса может перевести предоставленный номер, на экране будет отображаться переведенный номер.</span><span class="sxs-lookup"><span data-stu-id="0814a-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="0814a-132">транслатеднумбер</span><span class="sxs-lookup"><span data-stu-id="0814a-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="0814a-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="0814a-133">\+12065551219</span></span>

<span data-ttu-id="0814a-134">Если проверка завершится ошибкой, будет возвращено пустое переведенное число.</span><span class="sxs-lookup"><span data-stu-id="0814a-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="0814a-135">транслатеднумбер</span><span class="sxs-lookup"><span data-stu-id="0814a-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0814a-136">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="0814a-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="0814a-137">Если тест-Ксвоиценормализатионруле возвращает переведенное число, которое означает, что указанное правило нормализации голоса не смогло перевести предоставленный телефонный номер в формат E. 164, используемый Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0814a-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="0814a-138">Чтобы убедиться в том, что вы ввели правильный номер телефона, убедитесь в том, что он правильно введен.</span><span class="sxs-lookup"><span data-stu-id="0814a-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="0814a-139">Например, вы ожидаете, что правило нормализации голоса будет иметь проблемы при преобразовании числа, похожего на следующее:</span><span class="sxs-lookup"><span data-stu-id="0814a-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="0814a-140">Если номер введен правильно, необходимо убедиться в том, что указанное правило нормализации предназначено для обработки этого номера телефона.</span><span class="sxs-lookup"><span data-stu-id="0814a-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="0814a-141">Например, одно правило нормализации может быть спроектировано для обработки формата 12065551219, но второе правило может быть спроектировано для обработки числа 2065551219.</span><span class="sxs-lookup"><span data-stu-id="0814a-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="0814a-142">(Это тот же самый и тот же номер телефона, но и код страны 1 в самом начале.) Чтобы получить подробные сведения о правиле нормализации голосовой связи, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="0814a-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="0814a-143">Чтобы получить подробные сведения о всех правилах нормализации голоса, выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="0814a-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0814a-144">См. также</span><span class="sxs-lookup"><span data-stu-id="0814a-144">See Also</span></span>


[<span data-ttu-id="0814a-145">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="0814a-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

