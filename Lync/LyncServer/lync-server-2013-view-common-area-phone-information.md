---
title: 'Lync Server 2013: Просмотр сведений о стандартном телефоне'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900beb4f96fd71e0e6a4ded40d776f1e7d356529
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Просмотр сведений о стандартном телефоне в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

С помощью командлета **Get-кскоммонареафоне** вы можете просматривать сведения об общих телефонах, настроенных для использования в вашей организации. При использовании без параметров этот командлет возвращает сведения обо всех ваших стандартных телефонах. Необязательные параметры предоставляют различные способы фильтрации данных. Например, вы можете получить доступ ко всем общим телефонам, которые содержат объекты контактов в указанном подразделении (OU) или все объекты контактов, находящиеся в указанном здании. Дополнительные сведения о параметрах **Get-кскоммонареафоне** можно найти в [статьях Get-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).

Запустите **Get-кскоммонареафоне** либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>Просмотр сведений обо всех общих телефонах с областями

  - Чтобы просмотреть сведения обо всех обычных телефонах, введите в командной консоли Lync Server указанную ниже команду и нажмите клавишу ВВОД.
    
        Get-CsCommonAreaPhone
    
    Вы получите примерно такую информацию:
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

