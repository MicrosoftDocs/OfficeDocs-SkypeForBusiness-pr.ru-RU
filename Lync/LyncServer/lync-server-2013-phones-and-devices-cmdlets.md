---
title: 'Командлеты для Lync Server 2013: телефоны и устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5e698c23c87f679302c6612bec138bcbae39f71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ece18-102">Командлеты для телефонов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece18-102">Phones and devices cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ece18-103">_**Тема последнего изменения:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="ece18-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="ece18-104">Microsoft Lync Server 2013 предоставляет множество командлетов, позволяющих управлять телефонными и другими устройствами.</span><span class="sxs-lookup"><span data-stu-id="ece18-104">Microsoft Lync Server 2013 provides a number of cmdlets that enable you to manage telephones and other hardware devices.</span></span> <span data-ttu-id="ece18-105">Сюда входят телефоны для передачи голоса по протоколу IP (VoIP). обычные телефоны (например, Телефон в здании, кафетериа или другое общедоступное место); и даже аналоговые телефоны, телефоны, на которых не может работать Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ece18-105">This includes such things as Voice over IP (VoIP) phones; common area phones (for example, a phone in a building lobby, cafeteria, or other public location); and even analog phones, phones that are not capable of running Lync Phone Edition.</span></span>

<div>

## <a name="phones-and-devices-cmdlets"></a><span data-ttu-id="ece18-106">Командлеты для телефонов и устройств</span><span class="sxs-lookup"><span data-stu-id="ece18-106">Phones and Devices Cmdlets</span></span>

<span data-ttu-id="ece18-107">Командлеты **ксдевицеупдате** используются для управления веб-службой обновления устройства, компонентом Lync Server, который позволяет администраторам распространять обновления микропрограмм на телефоны и другие устройства с Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ece18-107">The **CsDeviceUpdate** cmdlets are used to manage the Device Update Web service, a Lync Server component that enables administrators to distribute firmware updates to telephones and other devices running Lync Phone Edition.</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-108">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-108">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-109">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-109">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-110">[New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-110">[New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-112">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-112">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-118">[Get-Ксукфонеконфигуратион](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-125">[Remove-Ксдевицеупдатеконфигуратион](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-125">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-129">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-129">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-132">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-132">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ece18-135">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-135">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-136">[New-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-136">[New-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-137">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-137">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ece18-138">[Set-Кстестдевице](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ece18-138">[Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ece18-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ece18-139">See Also</span></span>


[<span data-ttu-id="ece18-140">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ece18-140">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

