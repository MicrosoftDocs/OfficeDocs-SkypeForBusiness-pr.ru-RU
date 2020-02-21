---
title: 'Lync Server 2013: создание или изменение объекта контакта устройства конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74808a2deae4f7fa52e1a48fcbd415205eca93cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="07e5b-102">Создание или изменение объекта контакта устройства конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07e5b-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07e5b-103">_**Последнее изменение темы:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="07e5b-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="07e5b-104">Чтобы создать объект комнаты конференц-связи, сначала создайте учетную запись пользователя Active Directory для представления устройства.</span><span class="sxs-lookup"><span data-stu-id="07e5b-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="07e5b-105">Затем используйте командлет **Enable-CsMeetingRoom** , чтобы эта учетная запись функционировала как устройство конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="07e5b-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="07e5b-106">Если требуется изменить свойства существующего устройства для конференц-связи, используйте командлет **Set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="07e5b-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="07e5b-107">Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07e5b-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07e5b-108">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="07e5b-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="07e5b-109">Создание устройства конференц-связи</span><span class="sxs-lookup"><span data-stu-id="07e5b-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="07e5b-110">После создания учетной записи пользователя Active Directory, которая представляет новое устройство для конференц-связи, включите ее с помощью командлета **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="07e5b-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="07e5b-111">Убедитесь, что вы включили a) идентификацию устройства конференц-связи, b) пул регистратора, в котором будет размещена учетная запись комнаты, и c) SIP-адрес, назначаемый этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="07e5b-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="07e5b-112">Например:</span><span class="sxs-lookup"><span data-stu-id="07e5b-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="07e5b-113">Изменение устройства конференц-связи</span><span class="sxs-lookup"><span data-stu-id="07e5b-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="07e5b-114">Чтобы изменить значения свойств существующего устройства для конференц-связи, используйте командлет **Set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="07e5b-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="07e5b-115">Например, следующая команда обновляет номер телефона (LineUri), связанный с устройством конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="07e5b-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="07e5b-116">Дополнительные сведения можно найти в разделах справки для командлета [Enable – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) и командлета [Set – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="07e5b-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

