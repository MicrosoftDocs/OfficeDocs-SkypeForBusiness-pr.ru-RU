---
title: 'Lync Server 2013: Проверка конфигурации магистрали по номеру телефона'
description: 'Lync Server 2013: Проверка конфигурации магистрали по номеру телефона.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdfe1a2a9c5c87310ad561464960c5a01fea7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543545"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="e7489-103">Проверка конфигурации магистрали по номеру телефона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7489-103">Check trunk configuration against a phone number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7489-104">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="e7489-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7489-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="e7489-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e7489-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="e7489-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7489-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="e7489-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e7489-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7489-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7489-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="e7489-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e7489-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e7489-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e7489-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e7489-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="e7489-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7489-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e7489-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e7489-113">Description</span></span>

<span data-ttu-id="e7489-114">Магистральные линии SIP соединяют внутреннюю корпоративную сеть Lync Server с одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="e7489-114">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="e7489-115">Телефонная сеть общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="e7489-115">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="e7489-116">УАТС (IP-открытая ветвь).</span><span class="sxs-lookup"><span data-stu-id="e7489-116">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="e7489-117">Пограничный контроллер сеансов (SBC).</span><span class="sxs-lookup"><span data-stu-id="e7489-117">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="e7489-118">Командлет Test-CsTrunkConfiguration проверяет, может ли телефонный номер (набираемый пользователем) быть преобразован в сеть E. 164 и направляться по указанной магистральной линии SIP.</span><span class="sxs-lookup"><span data-stu-id="e7489-118">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e7489-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="e7489-119">Running the test</span></span>

<span data-ttu-id="e7489-120">Для запуска командлета Test-CsTrunkConfiguration сначала необходимо использовать командлет Get-CsTrunkConfiguration, чтобы получить экземпляр параметров конфигурации магистральной сети SIP; Затем этот экземпляр передается в командлет Test-CsTrunkConfiguration:</span><span class="sxs-lookup"><span data-stu-id="e7489-120">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="e7489-121">Выполнение Test-CsTrunkConfiguration без первого запуска Get-CsTrunkConfiguration не будет работать.</span><span class="sxs-lookup"><span data-stu-id="e7489-121">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="e7489-122">Например, эта команда завершится с ошибками, не возвращая никаких данных:</span><span class="sxs-lookup"><span data-stu-id="e7489-122">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="e7489-123">Если у вас есть несколько семейств параметров конфигурации магистрали SIP, вы можете использовать следующую команду для проверки каждой из них с одним и тем же номером телефона:</span><span class="sxs-lookup"><span data-stu-id="e7489-123">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="e7489-124">Для получения дополнительных сведений обратитесь к справочной документации по командлету Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e7489-124">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e7489-125">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="e7489-125">Determining success or failure</span></span>

<span data-ttu-id="e7489-126">Если Test-CsTrunkConfiguration может позвонить на набранный номер, переведенный номер телефона (в формате E. 164) и правило, используемое для перевода этого номера телефона, будут отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="e7489-126">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="e7489-127">Транслатеднумбер Матчингруле</span><span class="sxs-lookup"><span data-stu-id="e7489-127">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="e7489-128">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="e7489-128">\---------------- ------------</span></span>

<span data-ttu-id="e7489-129">\+12065551219 Global/Redmond</span><span class="sxs-lookup"><span data-stu-id="e7489-129">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="e7489-130">Если тест завершается неудачей, Test-CsTrunkConfiguration возвращает пустые значения свойств:</span><span class="sxs-lookup"><span data-stu-id="e7489-130">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="e7489-131">Транслатеднумбер Матчингруле</span><span class="sxs-lookup"><span data-stu-id="e7489-131">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="e7489-132">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="e7489-132">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e7489-133">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="e7489-133">Reasons why the test might have failed</span></span>

<span data-ttu-id="e7489-134">Если Test-CsTrunkConfiguration не возвращает соответствующее значение, которое обычно означает, что тестируемые параметры конфигурации магистрали не имеют правила преобразования исходящих вызовов для преобразования набранных номеров в формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="e7489-134">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="e7489-135">Чтобы получить правила преобразования, назначенные для коллекции параметров конфигурации магистрали, можно использовать следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e7489-135">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="e7489-136">Для каждого правила преобразования возвращаются сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="e7489-136">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="e7489-137">Описание: номера телефонов без кода страны или города.</span><span class="sxs-lookup"><span data-stu-id="e7489-137">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="e7489-138">Шаблон: ^ \\ + ( \\ d \* ) $</span><span class="sxs-lookup"><span data-stu-id="e7489-138">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="e7489-139">Name: Ноареакоде</span><span class="sxs-lookup"><span data-stu-id="e7489-139">Name : NoAreaCode</span></span>

<span data-ttu-id="e7489-140">На этом шаге необходимо проверить значение свойства Pattern (это строка [регулярного выражения](https://go.microsoft.com/fwlink/?linkid=400464) ), чтобы проверить, настроены ли какие-либо правила преобразования для обработки набора номера.</span><span class="sxs-lookup"><span data-stu-id="e7489-140">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="e7489-141">В противном случае необходимо изменить одно из существующих правил (Set-CsOutboundTranslationRule) или использовать командлет New-CsOutboundTranslationRule, чтобы добавить новое правило в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e7489-141">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7489-142">См. также</span><span class="sxs-lookup"><span data-stu-id="e7489-142">See Also</span></span>


[<span data-ttu-id="e7489-143">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7489-143">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

