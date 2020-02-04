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
ms.openlocfilehash: 56d594f0bf6e393545f4a7c29785b5f66b328bdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="01040-102">Создание или изменение объекта контакта устройства конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01040-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01040-103">_**Тема последнего изменения:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="01040-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="01040-104">Чтобы создать объект комнаты конференц-связи, сначала создайте учетную запись пользователя Active Directory для представления устройства.</span><span class="sxs-lookup"><span data-stu-id="01040-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="01040-105">Затем используйте командлет **Enable-ксмитингрум** , чтобы разрешить этой учетной записи работать в качестве устройства конференций.</span><span class="sxs-lookup"><span data-stu-id="01040-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="01040-106">Если вам нужно изменить свойства существующего устройства конференц-связи, используйте командлет **Set – ксмитингрум** .</span><span class="sxs-lookup"><span data-stu-id="01040-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="01040-107">Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01040-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01040-108">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01040-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="01040-109">Создание устройства конференц-связи</span><span class="sxs-lookup"><span data-stu-id="01040-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="01040-110">После создания учетной записи пользователя Active Directory, которая представляет новое устройство для проведения конференций, включите ее с помощью командлета **Enable-ксмитингрум** .</span><span class="sxs-lookup"><span data-stu-id="01040-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="01040-111">Убедитесь в том, что вы хотите добавить учетную запись, b) в пул регистраторов, в котором будет храниться счет комнаты и c) адрес SIP, назначаемый этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="01040-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="01040-112">Например:</span><span class="sxs-lookup"><span data-stu-id="01040-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="01040-113">Изменение устройства конференц-связи</span><span class="sxs-lookup"><span data-stu-id="01040-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="01040-114">Чтобы изменить значения свойств существующего устройства конференции, используйте командлет **Set-ксмитингрум** .</span><span class="sxs-lookup"><span data-stu-id="01040-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="01040-115">Например, следующая команда обновляет номер телефона (Линеури), связанный с устройством конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="01040-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="01040-116">Подробные сведения можно найти в разделах справки по командлетам [Enable-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) и командлету [Set-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="01040-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

