---
title: 'Lync Server 2013: Проверка правил нормализации голосовой связи'
description: 'Lync Server 2013: проверьте правила нормализации голосовых вызовов.'
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
ms.openlocfilehash: f68bbde24a3dc7d8e8214dcfe506d4b8112fbbb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543535"
---
# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="22889-103">Проверка правил нормализации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22889-103">Check voice normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22889-104">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="22889-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22889-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="22889-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="22889-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="22889-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22889-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="22889-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="22889-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22889-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22889-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="22889-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="22889-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="22889-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="22889-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="22889-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="22889-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="22889-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="22889-113">Описание</span><span class="sxs-lookup"><span data-stu-id="22889-113">Description</span></span>

<span data-ttu-id="22889-114">Правила нормализации голосовой связи используются для преобразования телефонного номера, набранного пользователем (например, 2065551219), в формат E. 164, используемый Lync Server (+ 12065551219).</span><span class="sxs-lookup"><span data-stu-id="22889-114">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="22889-115">Например, если пользователь набирает номер телефона, не включая код страны или код города (например, 5551219), необходимо создать правило нормализации голосовой связи, которое может преобразовать этот номер в формат E. 164: + 12065551219.</span><span class="sxs-lookup"><span data-stu-id="22889-115">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="22889-116">Без такого правила пользователь не сможет вызвать 555-1219.</span><span class="sxs-lookup"><span data-stu-id="22889-116">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="22889-117">Командлет Test-CsVoiceNormalizationRule проверяет, может ли указанное правило нормализации голоса успешно преобразовывать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="22889-117">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="22889-118">Например, эта команда проверяет, можно ли нормализовать глобальное правило нормализации Ноареакоде и конвертировать строку набора 5551219.</span><span class="sxs-lookup"><span data-stu-id="22889-118">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="22889-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="22889-119">Running the test</span></span>

<span data-ttu-id="22889-120">Для запуска командлета Test-CsVoiceNormalizationRule сначала необходимо использовать командлет Get-CsVoiceNormalizationRule, чтобы получить экземпляр тестируемого правила, а затем передать его в Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="22889-120">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="22889-121">Синтаксис, похожий на этот, не работает:</span><span class="sxs-lookup"><span data-stu-id="22889-121">Syntax similar to this won't work:</span></span>

<span data-ttu-id="22889-122">Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "Global/prefix ALL"</span><span class="sxs-lookup"><span data-stu-id="22889-122">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="22889-123">Вместо этого используйте синтаксис, аналогичный приведенному ниже, который объединяет командлеты Get-CsVoiceNormalizationRule и Test-CsVoiceNormalizationRule:</span><span class="sxs-lookup"><span data-stu-id="22889-123">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="22889-124">Get-CsVoiceNormalizationRule-Identity "Global/prefix ALL" | Test-CsVoiceNormalizationRule DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="22889-124">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22889-125">.</span><span class="sxs-lookup"><span data-stu-id="22889-125">.</span></span> <span data-ttu-id="22889-126">Кроме того, вы также можете использовать этот подход, чтобы получить экземпляр правила, а затем проверить это правило по указанному номеру телефона:</span><span class="sxs-lookup"><span data-stu-id="22889-126">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="22889-127">Введите значение параметра DialedNumber в точности так, как ожидается набираемый номер.</span><span class="sxs-lookup"><span data-stu-id="22889-127">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="22889-128">Например, если указанное правило нормализации голосовой связи должно автоматически добавлять код страны (первый 1 в значении 12065551219), то не следует оставлять код страны:</span><span class="sxs-lookup"><span data-stu-id="22889-128">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="22889-129">Если правило настроено правильно, оно автоматически добавляет код страны при преобразовании номера в формат E. 164, используемый Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22889-129">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="22889-130">Для получения дополнительных сведений обратитесь к справочной документации по командлету Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="22889-130">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="22889-131">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="22889-131">Determining success or failure</span></span>

<span data-ttu-id="22889-132">Если указанное правило нормализации голосовой связи может переводить предоставленный номер, переведенный номер будет отображаться на экране:</span><span class="sxs-lookup"><span data-stu-id="22889-132">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="22889-133">транслатеднумбер</span><span class="sxs-lookup"><span data-stu-id="22889-133">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="22889-134">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="22889-134">\+12065551219</span></span>

<span data-ttu-id="22889-135">Если тест завершается неудачей, возвращается пустой переведенный номер:</span><span class="sxs-lookup"><span data-stu-id="22889-135">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="22889-136">транслатеднумбер</span><span class="sxs-lookup"><span data-stu-id="22889-136">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="22889-137">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="22889-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="22889-138">Если Test-CsVoiceNormalizationRule возвращает переведенный номер, который означает, что указанное правило нормализации голосовой связи не смогло преобразовать предоставленный телефонный номер в формат E. 164, используемый Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22889-138">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="22889-139">Чтобы убедиться в этом, сначала убедитесь, что номер телефона введен правильно.</span><span class="sxs-lookup"><span data-stu-id="22889-139">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="22889-140">Например, вы ожидаете, что правило нормализации голоса будет иметь проблемы при преобразовании числа, аналогичного следующему:</span><span class="sxs-lookup"><span data-stu-id="22889-140">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="22889-141">Если номер введен правильно, необходимо убедиться, что указанное правило нормализации предназначено для обработки этого номера телефона.</span><span class="sxs-lookup"><span data-stu-id="22889-141">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="22889-142">Например, одно правило нормализации может быть предназначено для обработки формата 12065551219, но второе правило может быть предназначено для обработки числа 2065551219.</span><span class="sxs-lookup"><span data-stu-id="22889-142">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="22889-143">(Это тот же номер телефона, но не код страны 1 в самом начале). Чтобы получить подробные сведения о правиле нормализации голосовой связи, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="22889-143">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="22889-144">Чтобы получить подробные сведения о всех правилах нормализации голосовой связи, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="22889-144">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22889-145">См. также</span><span class="sxs-lookup"><span data-stu-id="22889-145">See Also</span></span>


[<span data-ttu-id="22889-146">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="22889-146">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

