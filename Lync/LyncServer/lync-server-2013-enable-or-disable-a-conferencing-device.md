---
title: 'Lync Server 2013: Включение и отключение устройства для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a4a0f582f57d4e096001d508d3983facdded74c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="f48cc-102">Включение и отключение устройства конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f48cc-102">Enable or disable a conferencing device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f48cc-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f48cc-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f48cc-104">Включать и отключать устройства конференц-связи с помощью командлета **Enable – ксмитингрум** и командлета **Disable-ксмитингрум** .</span><span class="sxs-lookup"><span data-stu-id="f48cc-104">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="f48cc-105">Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f48cc-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f48cc-106">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f48cc-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="f48cc-107">Включение устройства для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="f48cc-107">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="f48cc-108">Чтобы включить устройство для проведения конференций, используйте командлет **Enable-ксмитингрум** .</span><span class="sxs-lookup"><span data-stu-id="f48cc-108">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="f48cc-109">При включении устройства для конференц-связи необходимо включить в него удостоверение устройства конференц-связи, b) пула регистраторов, в котором будет храниться учетная запись комнаты, и c) адрес SIP, назначаемый этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f48cc-109">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="f48cc-110">Отключение устройства конференц-связи</span><span class="sxs-lookup"><span data-stu-id="f48cc-110">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="f48cc-111">Чтобы отключить устройство для проведения конференций, используйте командлет **Disable-ксмитингрум** .</span><span class="sxs-lookup"><span data-stu-id="f48cc-111">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="f48cc-112">Убедитесь в том, что вы указали, что устройство конференц-связи будет отключено:</span><span class="sxs-lookup"><span data-stu-id="f48cc-112">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="f48cc-113">Подробные сведения можно найти в разделах справки по командлетам [Enable-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) и командлету [Disable-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="f48cc-113">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

