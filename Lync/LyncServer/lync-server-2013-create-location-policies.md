---
title: 'Lync Server 2013: создание политик расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eca6b5c2b4bb88ed1b611eedd831c5c30d14bbb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="83509-102">Создание политик расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83509-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83509-103">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="83509-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="83509-104">Lync Server использует политику расположения для включения клиентов Lync для E9 – 1 — 1 во время регистрации клиента.</span><span class="sxs-lookup"><span data-stu-id="83509-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="83509-105">Политика расположения содержит параметры, которые определяют порядок внедрения E9-1-1..</span><span class="sxs-lookup"><span data-stu-id="83509-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="83509-p102">Глобальную политику расположения можно редактировать, кроме того, можно создавать новые именованные политики расположения. Клиент получает глобальную политику, если он расположен не в подсети, для которой имеется связанная локальная политика, или если локальная политика не назначена ему напрямую. Именованные политики назначаются подсетям или пользователям.</span><span class="sxs-lookup"><span data-stu-id="83509-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="83509-109">Чтобы создать политику расположения, следует использовать учетную запись, являющуюся членом группы RTCUniversalServerAdmins или административной роли CsVoiceAdministrator или обладает эквивалентными правами и разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="83509-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="83509-110">Полное описание политик расположения приведено [в разделе Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="83509-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="83509-111">Командлеты в этой процедуре используют заданную политику расположения и приведенные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="83509-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83509-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="83509-112">Element</span></span></th>
<th><span data-ttu-id="83509-113">Значение</span><span class="sxs-lookup"><span data-stu-id="83509-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83509-114">енханцедемерженцисервицесенаблед</span><span class="sxs-lookup"><span data-stu-id="83509-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="83509-115"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="83509-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83509-116">локатионрекуиред</span><span class="sxs-lookup"><span data-stu-id="83509-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="83509-117"><strong>Заявление об отказе</strong></span><span class="sxs-lookup"><span data-stu-id="83509-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83509-118">енханцедемерженцисервицедисклаимер</span><span class="sxs-lookup"><span data-stu-id="83509-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="83509-p104">Политика вашей компании требует задать расположение. В противном случае в экстренной ситуации соответствующие службы не смогут определить ваше расположение. Задайте расположение.</span><span class="sxs-lookup"><span data-stu-id="83509-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83509-122">Параметра uselocationfore911only установлено</span><span class="sxs-lookup"><span data-stu-id="83509-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="83509-123"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="83509-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83509-124">Параметра pstnusage</span><span class="sxs-lookup"><span data-stu-id="83509-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="83509-125"><strong>емерженциусаже</strong></span><span class="sxs-lookup"><span data-stu-id="83509-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83509-126">емерженцидиалстринг</span><span class="sxs-lookup"><span data-stu-id="83509-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="83509-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="83509-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83509-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="83509-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="83509-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="83509-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83509-130">нотификатионури</span><span class="sxs-lookup"><span data-stu-id="83509-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="83509-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="83509-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83509-132">конференцеури</span><span class="sxs-lookup"><span data-stu-id="83509-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="83509-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="83509-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83509-134">конференцемоде</span><span class="sxs-lookup"><span data-stu-id="83509-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="83509-135"><strong>TwoWay</strong></span><span class="sxs-lookup"><span data-stu-id="83509-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83509-136">локатионрефрешинтервал</span><span class="sxs-lookup"><span data-stu-id="83509-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="83509-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="83509-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83509-138">Для получения подробных сведений о работе с политиками расположения обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="83509-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="83509-139">New — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="83509-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="83509-140">Get — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="83509-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="83509-141">Set — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="83509-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="83509-142">Remove — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="83509-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="83509-143">Granting — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="83509-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="83509-144">Создание политик расположения</span><span class="sxs-lookup"><span data-stu-id="83509-144">To create location policies</span></span>

1.  <span data-ttu-id="83509-145">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="83509-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83509-146">Командлет CsLocationPolicy завершится с ошибкой, если значение для параметра <STRONG>PstnUsage</STRONG> не будет содержаться в глобальном списке параметров PstnUsage.</span><span class="sxs-lookup"><span data-stu-id="83509-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="83509-147">Чтобы изменить глобальную политику расположения, можно дополнительно выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="83509-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="83509-148">Выполните следующие действия, чтобы создать именованную политику расположения.</span><span class="sxs-lookup"><span data-stu-id="83509-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="83509-149">Выполните следующий командлет, чтобы применить именованную политику расположения, созданную в шаге 3, к политике пользователя.</span><span class="sxs-lookup"><span data-stu-id="83509-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

