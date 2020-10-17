---
title: 'Lync Server 2013: Просмотр сведений о телефонах общей области'
description: 'Lync Server 2013: Просмотр сведений о телефонах общей области.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4debe9a76118ac0bf1ca711426ce5487009a053
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572475"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Просмотр сведений о телефонах общей области в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Вы можете просмотреть сведения о телефонах, настроенных для использования в Организации, с помощью командлета **Get – CsCommonAreaPhone** . При использовании без параметров этот командлет возвращает сведения обо всех телефонах, используемых в вашей сети. Необязательные параметры предоставляют различные способы фильтрации информации. Например, вы можете вернуть все телефонные телефоны с контактами в указанном подразделении или всех объектах Contacts, расположенных в указанном здании. Дополнительные сведения о параметрах **Get – CsCommonAreaPhone** можно найти в статье [Get – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).

Выполните командлет **Get – CsCommonAreaPhone** либо в командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>Просмотр сведений обо всех телефонах на общем участке

  - Чтобы просмотреть сведения обо всех телефонах вашей сети, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:
    
        Get-CsCommonAreaPhone
    
    Вы получите сведения, аналогичные приведенным ниже.
    
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

Дополнительные сведения см. в разделе справки по командлету [Get – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

