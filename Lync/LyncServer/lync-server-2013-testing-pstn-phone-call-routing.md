---
title: 'Lync Server 2013: Проверка маршрутизации звонков по телефонной сети PSTN'
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
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="3ec57-102">Проверка маршрутизации телефонных звонков PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ec57-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ec57-103">_**Тема последнего изменения:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="3ec57-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec57-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="3ec57-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3ec57-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="3ec57-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec57-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="3ec57-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3ec57-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ec57-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec57-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="3ec57-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3ec57-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="3ec57-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3ec57-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксинтертрункраутинг</strong> .</span><span class="sxs-lookup"><span data-stu-id="3ec57-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="3ec57-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3ec57-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3ec57-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3ec57-112">Description</span></span>

<span data-ttu-id="3ec57-113">Командлет **Test-ксинтертрункраутинг** подтверждает, что звонки могут маршрутизироваться от одного SIP к другому.</span><span class="sxs-lookup"><span data-stu-id="3ec57-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="3ec57-114">Для этого командлету задается номер телефона и конфигурация магистрали.</span><span class="sxs-lookup"><span data-stu-id="3ec57-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="3ec57-115">**Тест-ксинтертрункраутинг** будет указывать маршруты обратного сопоставления и использование PSTN для указанного номера.</span><span class="sxs-lookup"><span data-stu-id="3ec57-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="3ec57-116">Обратите внимание на то, что звонки между магистральами могут маршрутизироваться только в том случае, если в магистральных каналов есть шаблон номера, который соответствует указанному номеру телефона и только в том случае, если в магистральных каналов есть хотя бы одна PSTN.</span><span class="sxs-lookup"><span data-stu-id="3ec57-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3ec57-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="3ec57-117">Running the test</span></span>

<span data-ttu-id="3ec57-118">Команды, показанные ниже, возвращают подходящие маршруты и соответствующие использование телефона, позволяющие пользователям звонить по номеру 1-206-555-1219 с помощью параметров конфигурации канала для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="3ec57-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3ec57-119">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="3ec57-119">Determining success or failure</span></span>

<span data-ttu-id="3ec57-120">Если звонки могут маршрутизироваться от одного SIP к другому, вы получите вывод, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3ec57-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="3ec57-121">Фирстматчинграуте Матчингусаже Матчинграутес</span><span class="sxs-lookup"><span data-stu-id="3ec57-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="3ec57-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="3ec57-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="3ec57-123">Редмондрауте Локалусаже {Редмондрауте}</span><span class="sxs-lookup"><span data-stu-id="3ec57-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="3ec57-124">Если проверка завершилась сбоем, вы получите вывод примерно так:</span><span class="sxs-lookup"><span data-stu-id="3ec57-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="3ec57-125">Test-Ксинтертрункраутинг: не удается обработать Преобразование аргументов для параметра</span><span class="sxs-lookup"><span data-stu-id="3ec57-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="3ec57-126">"Трункконфигуратион".</span><span class="sxs-lookup"><span data-stu-id="3ec57-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="3ec57-127">Недопустимый Трункконфигуратионсеттинг (параметр).</span><span class="sxs-lookup"><span data-stu-id="3ec57-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="3ec57-128">Укажите</span><span class="sxs-lookup"><span data-stu-id="3ec57-128">Specify a</span></span>

<span data-ttu-id="3ec57-129">допустимый параметр (параметр) и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="3ec57-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="3ec57-130">В строке: 1 символ: 79</span><span class="sxs-lookup"><span data-stu-id="3ec57-130">At line:1 char:79</span></span>

<span data-ttu-id="3ec57-131">\+Test-Ксинтертрункраутинг-Таржетнумбер "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="3ec57-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="3ec57-132">\-Трункконфигуратион $t...</span><span class="sxs-lookup"><span data-stu-id="3ec57-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="3ec57-133">\+Категоринфо: Инвалиддата: (:) \[Test-ксинтертрункраутинг\], номинал</span><span class="sxs-lookup"><span data-stu-id="3ec57-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="3ec57-134">аметербиндингаргументтрансформатионексцептион</span><span class="sxs-lookup"><span data-stu-id="3ec57-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="3ec57-135">\+Фулликуалифиедеррорид: Параметераргументтрансформатионеррор, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="3ec57-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="3ec57-136">традиционно. Management. Voice. командлеты. Тестоксинтертрункраутингкмдлет</span><span class="sxs-lookup"><span data-stu-id="3ec57-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3ec57-137">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="3ec57-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="3ec57-138">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксинтертрункраутинг** :</span><span class="sxs-lookup"><span data-stu-id="3ec57-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="3ec57-139">Указаны недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="3ec57-139">You specified invalid parameters.</span></span> <span data-ttu-id="3ec57-140">Возможно, вы еще не настроили магистраль, а указанный конечный номер может быть неверным или недействительным.</span><span class="sxs-lookup"><span data-stu-id="3ec57-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ec57-141">См. также</span><span class="sxs-lookup"><span data-stu-id="3ec57-141">See Also</span></span>


[<span data-ttu-id="3ec57-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="3ec57-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="3ec57-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ec57-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

