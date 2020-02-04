---
title: 'Lync Server 2013: Просмотр сведений об устройствах конференции'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5355ae418e53c44cc61340b57910993ac2afea2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="e86e8-102">Просмотр сведений об устройствах конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e86e8-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e86e8-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e86e8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e86e8-104">С помощью Windows PowerShell и командлета **Get-ксмитингрум** вы можете просматривать сведения об устройствах для проведения конференций, настроенных для использования в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e86e8-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="e86e8-105">Запустите командлет **Get-ксмитингрум** либо в командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e86e8-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e86e8-106">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e86e8-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="e86e8-107">Если вы используете командлет **Get-ксмитингрум** без параметров, он возвращает сведения обо всех устройствах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e86e8-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="e86e8-108">Необязательные параметры предоставляют различные способы фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="e86e8-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="e86e8-109">Подробные сведения можно найти в разделе Параметры раздела [Get-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span><span class="sxs-lookup"><span data-stu-id="e86e8-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="e86e8-110">Просмотр сведений обо всех устройствах конференц-связи</span><span class="sxs-lookup"><span data-stu-id="e86e8-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="e86e8-111">Чтобы просмотреть сведения обо всех устройствах конференц-связи, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e86e8-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="e86e8-112">Этот командлет возвращает данные, подобные приведенным ниже, для каждого устройства Конференции.</span><span class="sxs-lookup"><span data-stu-id="e86e8-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="e86e8-113">Обратите внимание, что в этом примере показаны только некоторые сведения, которые можно увидеть при выполнении этого командлета:</span><span class="sxs-lookup"><span data-stu-id="e86e8-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="e86e8-114">Просмотр сведений об определенном устройстве конференц-связи</span><span class="sxs-lookup"><span data-stu-id="e86e8-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="e86e8-115">Чтобы просмотреть сведения о конкретном устройстве конференц-связи, включите параметр Identity и удостоверение устройства конференц-связи (обычно отображаемое имя Active Directory).</span><span class="sxs-lookup"><span data-stu-id="e86e8-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="e86e8-116">Например:</span><span class="sxs-lookup"><span data-stu-id="e86e8-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="e86e8-117">Дополнительные сведения можно найти в разделе справки по командлету [Get-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="e86e8-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

