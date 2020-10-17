---
title: 'Lync Server 2013: Просмотр сведений об устройстве конференц-связи'
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
ms.openlocfilehash: 89744ec28a0c6c65615f41706b16d7053415723a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506536"
---
# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="c197b-102">Просмотр сведений о устройствах конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c197b-102">View conferencing device information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c197b-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="c197b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="c197b-104">Сведения об устройствах конференц-связи, настроенных для использования в Организации, можно просмотреть с помощью Windows PowerShell и командлета **Get-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="c197b-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="c197b-105">Выполните командлет **Get – CsMeetingRoom** в командной консоли Lync Server 2013 или удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c197b-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c197b-106">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="c197b-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="c197b-107">Если вы используете командлет **Get-CsMeetingRoom** без параметров, он возвращает сведения обо всех устройствах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c197b-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="c197b-108">Необязательные параметры предоставляют различные способы фильтрации информации.</span><span class="sxs-lookup"><span data-stu-id="c197b-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="c197b-109">Дополнительные сведения см. в разделе Parameters раздела [Get – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span><span class="sxs-lookup"><span data-stu-id="c197b-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="c197b-110">Просмотр сведений обо всех устройствах конференц-связи</span><span class="sxs-lookup"><span data-stu-id="c197b-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="c197b-111">Чтобы просмотреть сведения обо всех устройствах для конференц-связи, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="c197b-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="c197b-112">Этот командлет возвращает информацию, подобную приведенной ниже, для каждого устройства конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c197b-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="c197b-113">Обратите внимание, что в этом примере показаны только некоторые сведения, которые вы увидите при выполнении этого командлета:</span><span class="sxs-lookup"><span data-stu-id="c197b-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="c197b-114">Просмотр сведений о конкретном устройстве конференц-связи</span><span class="sxs-lookup"><span data-stu-id="c197b-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="c197b-115">Чтобы просмотреть сведения о конкретном устройстве конференц-связи, включите параметр Identity, а затем идентификатор устройства конференц-связи (обычно отображаемое имя Active Directory).</span><span class="sxs-lookup"><span data-stu-id="c197b-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="c197b-116">Например:</span><span class="sxs-lookup"><span data-stu-id="c197b-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="c197b-117">Дополнительные сведения см. в разделе справки по командлету [Get – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="c197b-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

