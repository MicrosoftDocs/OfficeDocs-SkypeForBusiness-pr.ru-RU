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

# <a name="view-conferencing-device-information-in-lync-server-2013"></a>Просмотр сведений об устройствах конференции в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

С помощью Windows PowerShell и командлета **Get-ксмитингрум** вы можете просматривать сведения об устройствах для проведения конференций, настроенных для использования в вашей организации. Запустите командлет **Get-ксмитингрум** либо в командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

Если вы используете командлет **Get-ксмитингрум** без параметров, он возвращает сведения обо всех устройствах конференц-связи. Необязательные параметры предоставляют различные способы фильтрации данных. Подробные сведения можно найти в разделе Параметры раздела [Get-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>Просмотр сведений обо всех устройствах конференц-связи

  - Чтобы просмотреть сведения обо всех устройствах конференц-связи, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.
    
        Get-CsMeetingRoom
    
    Этот командлет возвращает данные, подобные приведенным ниже, для каждого устройства Конференции. Обратите внимание, что в этом примере показаны только некоторые сведения, которые можно увидеть при выполнении этого командлета:
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a>Просмотр сведений об определенном устройстве конференц-связи

  - Чтобы просмотреть сведения о конкретном устройстве конференц-связи, включите параметр Identity и удостоверение устройства конференц-связи (обычно отображаемое имя Active Directory). Например:
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

