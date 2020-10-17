---
title: 'Lync Server 2013: тестирование маршрутизации телефонных звонков PSTN'
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
ms.openlocfilehash: fe6f0b1da87cfff6033840d37f590922c0a3bd9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504006"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="478f8-102">Тестирование маршрутизации телефонных звонков PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="478f8-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="478f8-103">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="478f8-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="478f8-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="478f8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="478f8-105">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="478f8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="478f8-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="478f8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="478f8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="478f8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="478f8-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="478f8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="478f8-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="478f8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="478f8-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="478f8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="478f8-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="478f8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="478f8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="478f8-112">Description</span></span>

<span data-ttu-id="478f8-113">Командлет **Test-CsInterTrunkRouting** проверяет, могут ли вызовы маршрутизироваться от одного SIP к другому.</span><span class="sxs-lookup"><span data-stu-id="478f8-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="478f8-114">Для этого для командлета задается телефонный номер и конфигурация магистрали.</span><span class="sxs-lookup"><span data-stu-id="478f8-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="478f8-115">После этого **Test-CsInterTrunkRouting** сообщит о маршрутах обратного совпадения и использовании PSTN для указанного номера.</span><span class="sxs-lookup"><span data-stu-id="478f8-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="478f8-116">Обратите внимание на то, что звонки могут маршрутизироваться между магистральными каналами, только если они имеют шаблон номера, соответствующий указанному номеру телефона и только тогда, когда магистрали имеют по крайней мере одно использование PSTN.</span><span class="sxs-lookup"><span data-stu-id="478f8-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="478f8-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="478f8-117">Running the test</span></span>

<span data-ttu-id="478f8-118">Команды, показанные ниже, возвращают подходящие маршруты и подходящие способы использования телефонов, которые позволяют пользователям звонить по телефону 1-206-555-1219 с помощью параметров конфигурации магистрали для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="478f8-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="478f8-119">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="478f8-119">Determining success or failure</span></span>

<span data-ttu-id="478f8-120">Если звонки могут маршрутизироваться от одного SIP к другому, будет выведен результат, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="478f8-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="478f8-121">Фирстматчинграуте Матчингусаже Матчинграутес</span><span class="sxs-lookup"><span data-stu-id="478f8-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="478f8-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="478f8-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="478f8-123">Редмондрауте Локалусаже {Редмондрауте}</span><span class="sxs-lookup"><span data-stu-id="478f8-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="478f8-124">Если проверка завершилась неудачно, будет выведен результат, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="478f8-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="478f8-125">Test-CsInterTrunkRouting: не удается обработать Преобразование аргументов для параметра</span><span class="sxs-lookup"><span data-stu-id="478f8-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="478f8-126">"TrunkConfiguration".</span><span class="sxs-lookup"><span data-stu-id="478f8-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="478f8-127">Недопустимый Трункконфигуратионсеттинг (параметр).</span><span class="sxs-lookup"><span data-stu-id="478f8-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="478f8-128">Указать</span><span class="sxs-lookup"><span data-stu-id="478f8-128">Specify a</span></span>

<span data-ttu-id="478f8-129">допустимый параметр (параметр), а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="478f8-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="478f8-130">В строке: 1 символ: 79</span><span class="sxs-lookup"><span data-stu-id="478f8-130">At line:1 char:79</span></span>

<span data-ttu-id="478f8-131">\+ Test-CsInterTrunkRouting Таржетнумбер "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="478f8-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="478f8-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="478f8-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="478f8-133">\+ Категоринфо: Инвалиддата: (:) \[ Test-CsInterTrunkRouting \] , номинал</span><span class="sxs-lookup"><span data-stu-id="478f8-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="478f8-134">аметербиндингаргументтрансформатионексцептион</span><span class="sxs-lookup"><span data-stu-id="478f8-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="478f8-135">\+ Фулликуалифиедеррорид: Параметераргументтрансформатионеррор, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="478f8-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="478f8-136">технически. Management. Voice. командлеты. Тестоксинтертрункраутингкмдлет</span><span class="sxs-lookup"><span data-stu-id="478f8-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="478f8-137">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="478f8-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="478f8-138">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsInterTrunkRouting** :</span><span class="sxs-lookup"><span data-stu-id="478f8-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="478f8-139">Указаны недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="478f8-139">You specified invalid parameters.</span></span> <span data-ttu-id="478f8-140">Магистраль еще не настроен правильно, а указанный целевой номер может быть неверным или недопустимым.</span><span class="sxs-lookup"><span data-stu-id="478f8-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="478f8-141">См. также</span><span class="sxs-lookup"><span data-stu-id="478f8-141">See Also</span></span>


[<span data-ttu-id="478f8-142">Get — CsTrunk</span><span class="sxs-lookup"><span data-stu-id="478f8-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="478f8-143">Get — CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="478f8-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

