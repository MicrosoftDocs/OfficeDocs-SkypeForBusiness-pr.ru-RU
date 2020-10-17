---
title: 'Lync Server 2013: тестирование маршрутизации телефонных звонков PSTN'
description: 'Lync Server 2013: тестирование маршрутизации телефонных звонков PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556275"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="8bbe6-103">Тестирование маршрутизации телефонных звонков PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bbe6-103">Testing PSTN phone call routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bbe6-104">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="8bbe6-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bbe6-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="8bbe6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8bbe6-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="8bbe6-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bbe6-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="8bbe6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8bbe6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bbe6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bbe6-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="8bbe6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8bbe6-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8bbe6-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="8bbe6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="8bbe6-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8bbe6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8bbe6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8bbe6-113">Description</span></span>

<span data-ttu-id="8bbe6-114">Командлет **Test-CsInterTrunkRouting** проверяет, могут ли вызовы маршрутизироваться от одного SIP к другому.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-114">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="8bbe6-115">Для этого для командлета задается телефонный номер и конфигурация магистрали.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-115">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="8bbe6-116">После этого **Test-CsInterTrunkRouting** сообщит о маршрутах обратного совпадения и использовании PSTN для указанного номера.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-116">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="8bbe6-117">Обратите внимание на то, что звонки могут маршрутизироваться между магистральными каналами, только если они имеют шаблон номера, соответствующий указанному номеру телефона и только тогда, когда магистрали имеют по крайней мере одно использование PSTN.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-117">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8bbe6-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="8bbe6-118">Running the test</span></span>

<span data-ttu-id="8bbe6-119">Команды, показанные ниже, возвращают подходящие маршруты и подходящие способы использования телефонов, которые позволяют пользователям звонить по телефону 1-206-555-1219 с помощью параметров конфигурации магистрали для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-119">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8bbe6-120">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="8bbe6-120">Determining success or failure</span></span>

<span data-ttu-id="8bbe6-121">Если звонки могут маршрутизироваться от одного SIP к другому, будет выведен результат, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="8bbe6-121">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="8bbe6-122">Фирстматчинграуте Матчингусаже Матчинграутес</span><span class="sxs-lookup"><span data-stu-id="8bbe6-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="8bbe6-123">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="8bbe6-123">\------------------ ------------- --------------</span></span>

<span data-ttu-id="8bbe6-124">Редмондрауте Локалусаже {Редмондрауте}</span><span class="sxs-lookup"><span data-stu-id="8bbe6-124">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="8bbe6-125">Если проверка завершилась неудачно, будет выведен результат, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="8bbe6-125">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="8bbe6-126">Test-CsInterTrunkRouting: не удается обработать Преобразование аргументов для параметра</span><span class="sxs-lookup"><span data-stu-id="8bbe6-126">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="8bbe6-127">"TrunkConfiguration".</span><span class="sxs-lookup"><span data-stu-id="8bbe6-127">'TrunkConfiguration'.</span></span> <span data-ttu-id="8bbe6-128">Недопустимый Трункконфигуратионсеттинг (параметр).</span><span class="sxs-lookup"><span data-stu-id="8bbe6-128">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="8bbe6-129">Указать</span><span class="sxs-lookup"><span data-stu-id="8bbe6-129">Specify a</span></span>

<span data-ttu-id="8bbe6-130">допустимый параметр (параметр), а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-130">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="8bbe6-131">В строке: 1 символ: 79</span><span class="sxs-lookup"><span data-stu-id="8bbe6-131">At line:1 char:79</span></span>

<span data-ttu-id="8bbe6-132">\+ Test-CsInterTrunkRouting Таржетнумбер "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="8bbe6-132">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="8bbe6-133">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="8bbe6-133">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="8bbe6-134">\+ Категоринфо: Инвалиддата: (:) \[ Test-CsInterTrunkRouting \] , номинал</span><span class="sxs-lookup"><span data-stu-id="8bbe6-134">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="8bbe6-135">аметербиндингаргументтрансформатионексцептион</span><span class="sxs-lookup"><span data-stu-id="8bbe6-135">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="8bbe6-136">\+ Фулликуалифиедеррорид: Параметераргументтрансформатионеррор, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="8bbe6-136">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="8bbe6-137">технически. Management. Voice. командлеты. Тестоксинтертрункраутингкмдлет</span><span class="sxs-lookup"><span data-stu-id="8bbe6-137">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8bbe6-138">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="8bbe6-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="8bbe6-139">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsInterTrunkRouting** :</span><span class="sxs-lookup"><span data-stu-id="8bbe6-139">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="8bbe6-140">Указаны недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-140">You specified invalid parameters.</span></span> <span data-ttu-id="8bbe6-141">Магистраль еще не настроен правильно, а указанный целевой номер может быть неверным или недопустимым.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-141">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8bbe6-142">См. также</span><span class="sxs-lookup"><span data-stu-id="8bbe6-142">See Also</span></span>


[<span data-ttu-id="8bbe6-143">Get — CsTrunk</span><span class="sxs-lookup"><span data-stu-id="8bbe6-143">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="8bbe6-144">Get — CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8bbe6-144">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

