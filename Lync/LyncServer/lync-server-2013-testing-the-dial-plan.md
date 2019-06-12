---
title: 'Lync Server 2013: Проверка абонентской группы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2815248084e7591c11157cde3fb4851722315073
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="0912a-102">Проверка абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0912a-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0912a-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0912a-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0912a-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="0912a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0912a-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="0912a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0912a-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="0912a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0912a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0912a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0912a-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="0912a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0912a-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="0912a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0912a-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксдиалплан.</span><span class="sxs-lookup"><span data-stu-id="0912a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="0912a-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0912a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0912a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0912a-112">Description</span></span>

<span data-ttu-id="0912a-113">Командлет Test-Ксдиалплан позволяет видеть результаты применения абонентской группы к указанному номеру телефона.</span><span class="sxs-lookup"><span data-stu-id="0912a-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="0912a-114">Абонентские группы предоставляют сведения, например, как применяются правила нормализации, необходимые для того, чтобы пользователи корпоративной голосовой связи были звонить по телефону.</span><span class="sxs-lookup"><span data-stu-id="0912a-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="0912a-115">При наборе номера и абонентской группы этот командлет проверит, какое правило нормализации в абонентской группе будет применено, и что будет переведенный номер.</span><span class="sxs-lookup"><span data-stu-id="0912a-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="0912a-116">Вы можете использовать этот командлет для устранения проблем с преобразованиями чисел или для проверки того, как применять правила к определенным числам.</span><span class="sxs-lookup"><span data-stu-id="0912a-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0912a-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="0912a-117">Running the test</span></span>

<span data-ttu-id="0912a-118">Командлет Test-Ксдиалплан требует выполнения двух действий.</span><span class="sxs-lookup"><span data-stu-id="0912a-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="0912a-119">Сначала необходимо получить экземпляр тестируемой абонентской группы; Это можно сделать с помощью командлета Get-Ксдиалплан.</span><span class="sxs-lookup"><span data-stu-id="0912a-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="0912a-120">Во вторых, необходимо указать телефонный номер, который должен быть нормализован.</span><span class="sxs-lookup"><span data-stu-id="0912a-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="0912a-121">Формат, используемый для номера телефона, должен совпадать с номером, набранным и введенным пользователем.</span><span class="sxs-lookup"><span data-stu-id="0912a-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="0912a-122">Например, эта команда извлекает экземпляр абонентской группы RedmondDialPlan и проверяет, можно ли использовать номер телефона 12065551219.</span><span class="sxs-lookup"><span data-stu-id="0912a-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="0912a-123">Если у вас есть правило нормализации, которое автоматически добавляет код страны (в этом примере, 1) и код города (206), вам может потребоваться проверить номер телефона 5551219, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="0912a-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="0912a-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксдиалплан](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="0912a-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0912a-125">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="0912a-125">Determining success or failure</span></span>

<span data-ttu-id="0912a-126">Тест-Ксдиалплан отличается от многих командлетов тестирования Lync Server, так как он не только косвенно указывает, успешно ли прошел тест.</span><span class="sxs-lookup"><span data-stu-id="0912a-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="0912a-127">При использовании команды Test-Ксдиалплан вы не получаете обратные результаты, аналогичные таким образом, что приводит к четкому пометке:</span><span class="sxs-lookup"><span data-stu-id="0912a-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="0912a-128">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0912a-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0912a-129">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="0912a-129">Result : Success</span></span>

<span data-ttu-id="0912a-130">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="0912a-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="0912a-131">Ошибки</span><span class="sxs-lookup"><span data-stu-id="0912a-131">Error :</span></span>

<span data-ttu-id="0912a-132">Диагностик</span><span class="sxs-lookup"><span data-stu-id="0912a-132">Diagnosis :</span></span>

<span data-ttu-id="0912a-133">Вместо этого, если Test-Ксдиалплан завершается успешно, вы получите сведения о правиле нормализации, которое могло бы успешно перевести и использовать указанный номер телефона:</span><span class="sxs-lookup"><span data-stu-id="0912a-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="0912a-134">Транслатеднумбер: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="0912a-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="0912a-135">Матчингруле: описание =; Шаблон = ^ (\\d (11)) $; Перевод = + $1;</span><span class="sxs-lookup"><span data-stu-id="0912a-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="0912a-136">Name = prefix (префикс); Исинтерналекстенсион = false</span><span class="sxs-lookup"><span data-stu-id="0912a-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="0912a-137">Если при выполнении теста-Ксдиалплан возникла ошибка (то есть, если абонентская группа не имеет правила нормализации, которое может перевести указанный номер телефона), вы просто получите "пустой" выходной файл, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="0912a-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="0912a-138">Транслатеднумбер:</span><span class="sxs-lookup"><span data-stu-id="0912a-138">TranslatedNumber :</span></span>

<span data-ttu-id="0912a-139">Матчингруле:</span><span class="sxs-lookup"><span data-stu-id="0912a-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0912a-140">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="0912a-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="0912a-141">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксдиалплан:</span><span class="sxs-lookup"><span data-stu-id="0912a-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="0912a-142">Возможно, вы использовали неверный формат при указании номера телефона.</span><span class="sxs-lookup"><span data-stu-id="0912a-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="0912a-143">Абонентские планы включают правила нормализации, позволяющие серверу Lync Server переводить телефонные номера, набранные или введенные пользователем.</span><span class="sxs-lookup"><span data-stu-id="0912a-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="0912a-144">Поэтому абонентская группа должна иметь правила нормализации, соответствующие числам, которые пользователи могут набрать.</span><span class="sxs-lookup"><span data-stu-id="0912a-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="0912a-145">Например, если пользователь может набрать код страны, код города, а затем сам номер телефона, это означает, что абонентская группа должна иметь правило нормализации для обработки телефонных номеров, например:</span><span class="sxs-lookup"><span data-stu-id="0912a-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="0912a-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="0912a-146">12065551219</span></span>
    
    <span data-ttu-id="0912a-147">Тем не менее, если ввести неправильный номер телефона (например, выход из последней цифры), проверка-Ксдиалплан завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="0912a-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="0912a-148">Это не значит, что абонентская группа является неисправной, но из-за того, что вы ввели номер телефона, который не удается интерпретировать.</span><span class="sxs-lookup"><span data-stu-id="0912a-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

