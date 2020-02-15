---
title: 'Lync Server 2013: Включение или отключение функции горячей замены'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42da4f35c78e182ac988b1185bf797e3cb88ddd5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Включение и отключение функции "горячая" в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Вы можете настроить телефонные телефоны в качестве *телефонов для стационарных устройств*. С помощью стационарных телефонов пользователи могут входить в систему с помощью собственной учетной записи пользователя, а после входа в систему использовать функции Lync Server и собственные параметры профилей пользователей. Управление возможностью горячей замены осуществляется с помощью политик клиентов: чтобы включить или отключить функцию "горячего", необходимо изменить политики клиентов, используемые телефонными телефонами. Сведения о том, как определить политики конференц-связи, назначенные телефонным телефонам, можно узнать [в статье Просмотр сведений о телефонах общей области в Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Используйте параметр Енаблехотдескинг командлета **New – CSClientPolicy** или командлета **Set – CSClientPolicy** , чтобы включить или отключить функцию горячей замены на телефоне, как показано ниже. Выполните эти командлеты в командной консоли Lync Server 2013 или в удаленном сеансе Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>


<div>

## <a name="enabling-hot-desking"></a>Включение функции Hot Desk

  - Чтобы включить поддержку горячей замены для телефонного телефона общего пользования, необходимо изменить клиентскую политику, назначенную этому телефону (или набору телефонов).
    
    После определения политики, которую необходимо изменить, следующим шагом является использование командлета **Set-CsClientPolicy** для установки параметра Енаблехотдескинг в значение true. Пример:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Кроме того, вы можете использовать командлет **New – CsClientPolicy** для создания новой клиентской политики, обеспечивающей горячую службу. Пример:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> После создания этой политики ее необходимо назначить соответствующим телефонам общего пользования. Сведения о том, <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">как назначить политики в Lync Server 2013, можно найти на общем телефоне</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Отключение функции горячей замены

  - Чтобы отключить функцию горячей замены для телефонного телефона общего пользования, сбросьте параметр Енаблехотдескинг командлета **Set – CsClientPolicy** в значение по умолчанию, равное false. Пример:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Дополнительные сведения можно найти в разделах справки для командлета [New – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и командлета [Set – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

