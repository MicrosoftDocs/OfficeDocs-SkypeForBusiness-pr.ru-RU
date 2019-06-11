---
title: 'Lync Server 2013: создание политик расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f420d3b634df79411bbc72cd4c029f9b5d97e19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="3b18a-102">Создание политик местоположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b18a-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b18a-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="3b18a-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="3b18a-104">Lync Server использует политику расположения для включения клиентов Lync для E9-1-1 во время регистрации клиента.</span><span class="sxs-lookup"><span data-stu-id="3b18a-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="3b18a-105">Политика расположения содержит параметры, которые определяют порядок реализации E911.</span><span class="sxs-lookup"><span data-stu-id="3b18a-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="3b18a-p102">Глобальную политику расположения можно редактировать, кроме того, можно создавать новые именованные политики расположения. Клиент получает глобальную политику, если он расположен не в подсети, для которой имеется связанная локальная политика, или если локальная политика не назначена ему напрямую. Именованные политики назначаются подсетям или пользователям.  </span><span class="sxs-lookup"><span data-stu-id="3b18a-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="3b18a-109">Чтобы создать политику расположения, следует использовать учетную запись, являющуюся членом группы RTCUniversalServerAdmins или административной роли CsVoiceAdministrator или обладает эквивалентными правами и разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="3b18a-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="3b18a-110">Полное описание политик местоположений показано в разделе [Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3b18a-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="3b18a-111">Командлеты в этой процедуре используют политику расположения, определенную с помощью следующих значений:</span><span class="sxs-lookup"><span data-stu-id="3b18a-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b18a-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="3b18a-112">Element</span></span></th>
<th><span data-ttu-id="3b18a-113">Значение</span><span class="sxs-lookup"><span data-stu-id="3b18a-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b18a-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="3b18a-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="3b18a-115"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b18a-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="3b18a-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="3b18a-117"><strong>Заявление об отказе</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b18a-118">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="3b18a-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="3b18a-p104">Политика вашей компании требует задать расположение. В противном случае в экстренной ситуации соответствующие службы не смогут определить ваше расположение. Задайте расположение.</span><span class="sxs-lookup"><span data-stu-id="3b18a-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b18a-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="3b18a-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="3b18a-123"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b18a-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="3b18a-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="3b18a-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b18a-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="3b18a-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="3b18a-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b18a-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="3b18a-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="3b18a-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b18a-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="3b18a-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="3b18a-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b18a-132">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="3b18a-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="3b18a-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b18a-134">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="3b18a-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="3b18a-135"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b18a-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="3b18a-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="3b18a-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="3b18a-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3b18a-138">Подробные сведения о работе с политиками расположения можно найти в документации по оболочке управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="3b18a-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="3b18a-139">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3b18a-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="3b18a-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3b18a-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="3b18a-141">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3b18a-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="3b18a-142">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3b18a-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="3b18a-143">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3b18a-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="3b18a-144">Создание политик расположения</span><span class="sxs-lookup"><span data-stu-id="3b18a-144">To create location policies</span></span>

1.  <span data-ttu-id="3b18a-145">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3b18a-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b18a-146">Командлет CsLocationPolicy завершится с ошибкой, если значение для параметра <STRONG>PstnUsage</STRONG> не будет содержаться в глобальном списке параметров PstnUsage.</span><span class="sxs-lookup"><span data-stu-id="3b18a-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="3b18a-147">Чтобы изменить глобальную политику расположения, можно дополнительно выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="3b18a-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="3b18a-148">Выполните следующие действия, чтобы создать именованную политику расположения.</span><span class="sxs-lookup"><span data-stu-id="3b18a-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="3b18a-149">Выполните следующий командлет, чтобы применить именованную политику расположения, созданную в шаге 3, к политике пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b18a-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

