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
# <a name="view-conferencing-device-information-in-lync-server-2013"></a>Просмотр сведений о устройствах конференц-связи в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Сведения об устройствах конференц-связи, настроенных для использования в Организации, можно просмотреть с помощью Windows PowerShell и командлета **Get-CsMeetingRoom** . Выполните командлет **Get – CsMeetingRoom** в командной консоли Lync Server 2013 или удаленном сеансе Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

Если вы используете командлет **Get-CsMeetingRoom** без параметров, он возвращает сведения обо всех устройствах конференц-связи. Необязательные параметры предоставляют различные способы фильтрации информации. Дополнительные сведения см. в разделе Parameters раздела [Get – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>Просмотр сведений обо всех устройствах конференц-связи

  - Чтобы просмотреть сведения обо всех устройствах для конференц-связи, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:
    
        Get-CsMeetingRoom
    
    Этот командлет возвращает информацию, подобную приведенной ниже, для каждого устройства конференц-связи. Обратите внимание, что в этом примере показаны только некоторые сведения, которые вы увидите при выполнении этого командлета:
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a>Просмотр сведений о конкретном устройстве конференц-связи

  - Чтобы просмотреть сведения о конкретном устройстве конференц-связи, включите параметр Identity, а затем идентификатор устройства конференц-связи (обычно отображаемое имя Active Directory). Например:
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

Дополнительные сведения см. в разделе справки по командлету [Get – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

