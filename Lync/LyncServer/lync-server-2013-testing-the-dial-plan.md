---
title: 'Lync Server 2013: тестирование абонентской группы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a83f8058dd761386329c3c0bc58a50c4aef7bdb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="754d9-102">Тестирование абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754d9-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="754d9-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="754d9-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="754d9-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="754d9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="754d9-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="754d9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754d9-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="754d9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="754d9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="754d9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754d9-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="754d9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="754d9-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="754d9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="754d9-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="754d9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="754d9-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="754d9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="754d9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="754d9-112">Description</span></span>

<span data-ttu-id="754d9-113">Командлет Test-CsDialPlan позволяет просматривать результаты применения абонентской группы к заданному телефонному номеру.</span><span class="sxs-lookup"><span data-stu-id="754d9-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="754d9-114">Абонентские группы предоставляют сведения, например, способ применения правил нормализации, необходимые для того, чтобы пользователи корпоративной голосовой связи могли совершать телефонные звонки.</span><span class="sxs-lookup"><span data-stu-id="754d9-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="754d9-115">Принимая во внимание набранный номер и абонентскую группу, этот командлет будет проверять, какое правило нормализации в данной абонентской группе будет применяться, и каким будет преобразованный номер.</span><span class="sxs-lookup"><span data-stu-id="754d9-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="754d9-116">Этот командлет можно использовать для устранения неполадок, связанных с числом переводов, или для проверки применения правил к определенным числам.</span><span class="sxs-lookup"><span data-stu-id="754d9-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="754d9-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="754d9-117">Running the test</span></span>

<span data-ttu-id="754d9-118">Для командлета Test-CsDialPlan необходимо выполнить два действия.</span><span class="sxs-lookup"><span data-stu-id="754d9-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="754d9-119">Для начала необходимо получить тестируемый экземпляр абонентской группы; Это можно сделать с помощью командлета Get – CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="754d9-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="754d9-120">Во вторых, необходимо указать телефонный номер, который должен быть нормализован.</span><span class="sxs-lookup"><span data-stu-id="754d9-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="754d9-121">Формат, используемый для телефонного номера, должен быть таким, как номер, набранный или введенный пользователем.</span><span class="sxs-lookup"><span data-stu-id="754d9-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="754d9-122">Например, эта команда получает экземпляр абонентской группы абонентскую redmonddialplan и проверяет, можно ли нормализовать номер телефона 12065551219:</span><span class="sxs-lookup"><span data-stu-id="754d9-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="754d9-123">Если у вас есть правило нормализации, которое автоматически добавляет код страны (в этом примере 1) и код города (206), можно проверить номер телефона 5551219, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="754d9-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="754d9-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="754d9-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="754d9-125">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="754d9-125">Determining success or failure</span></span>

<span data-ttu-id="754d9-126">Test-CsDialPlan отличается от многих командлетов тестирования Lync Server, так как он только косвенно указывает, успешно ли выполнен тест или закончился неудачно.</span><span class="sxs-lookup"><span data-stu-id="754d9-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="754d9-127">При использовании Test-CsDialPlan вы не получаете обратные результаты, аналогичные приведенным ниже, в результате чего ясно отмеченные:</span><span class="sxs-lookup"><span data-stu-id="754d9-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="754d9-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="754d9-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="754d9-129">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="754d9-129">Result : Success</span></span>

<span data-ttu-id="754d9-130">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="754d9-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="754d9-131">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="754d9-131">Error :</span></span>

<span data-ttu-id="754d9-132">Диагност</span><span class="sxs-lookup"><span data-stu-id="754d9-132">Diagnosis :</span></span>

<span data-ttu-id="754d9-133">Вместо этого, если Test-CsDialPlan выполнен успешно, вы получите сведения о правиле нормализации, способном успешно перевести и использовать указанный номер телефона:</span><span class="sxs-lookup"><span data-stu-id="754d9-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="754d9-134">Транслатеднумбер: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="754d9-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="754d9-135">Матчингруле: Description =; Pattern = ^ (\\г (11)) $; Перевод = + $1;</span><span class="sxs-lookup"><span data-stu-id="754d9-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="754d9-136">Имя = префикс все; Исинтерналекстенсион = false</span><span class="sxs-lookup"><span data-stu-id="754d9-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="754d9-137">Если командлет Test-CsDialPlan завершается с ошибкой (то есть если для абонентской группы не задано правило нормализации, которое может выполнить перевод указанного номера телефона), вы просто получите "пустой" вывод, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="754d9-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="754d9-138">Транслатеднумбер:</span><span class="sxs-lookup"><span data-stu-id="754d9-138">TranslatedNumber :</span></span>

<span data-ttu-id="754d9-139">Матчингруле:</span><span class="sxs-lookup"><span data-stu-id="754d9-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="754d9-140">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="754d9-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="754d9-141">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsDialPlan:</span><span class="sxs-lookup"><span data-stu-id="754d9-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="754d9-142">При указании номера телефона вы могли использовать недопустимый формат.</span><span class="sxs-lookup"><span data-stu-id="754d9-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="754d9-143">Абонентские группы включают правила нормализации, которые обеспечивают Lync Server для преобразования телефонных номеров, набранных или вводимых пользователем.</span><span class="sxs-lookup"><span data-stu-id="754d9-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="754d9-144">Поэтому абонентская абонентская схема должна иметь правила нормализации, которые совпадают с числами, которые пользователи могут набирать.</span><span class="sxs-lookup"><span data-stu-id="754d9-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="754d9-145">Например, если пользователи могут набрать код страны, код города, а затем номер телефона, это означает, что абонентская абонентская абонентская схема должна иметь правило нормализации для обработки телефонных номеров, например:</span><span class="sxs-lookup"><span data-stu-id="754d9-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="754d9-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="754d9-146">12065551219</span></span>
    
    <span data-ttu-id="754d9-147">Однако при вводе неправильного номера телефона (например, при выходе из завершающей цифры), Test-CsDialPlan завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="754d9-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="754d9-148">Это связано с неисправностью абонентской группы, так как вы ввели номер телефона, который не может быть интерпретирован.</span><span class="sxs-lookup"><span data-stu-id="754d9-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

