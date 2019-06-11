---
title: 'Lync Server 2013: Включение и отключение поддержки горячей замены'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5d9f2d168a06b5624375dcd005da58b4d3d5fd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Включение и отключение функции поддержки горячей замены в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Вы можете настроить стандартные телефоны как стационарные *телефоны*. С помощью стационарных телефонов пользователи могут входить в свою учетную запись пользователя и после входа в нее использовать возможности сервера Lync и собственные параметры профиля пользователя. Управление горячим подключением осуществляется с помощью политик клиента: чтобы включить или отключить функцию горячей замены, необходимо изменить политики клиента, используемые вашими стандартными телефонами. Подробные сведения о том, как определить политики конференц-связи, назначенные на обычные телефоны, можно найти [в статьях Просмотр сведений о телефонах в Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Вы можете использовать параметр Енаблехотдескинг командлета **New-CSClientPolicy** или командлет **Set-CSClientPolicy** , чтобы включить или отключить функцию горячей замены на телефоне, как описано ниже. Выполните эти командлеты либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>


<div>

## <a name="enabling-hot-desking"></a>Включение поддержки горячей замены

  - Чтобы включить функцию горячего подключения для обычного телефонного телефона, необходимо изменить политику клиента, назначенную этому телефону (или набору телефонов).
    
    После того как вы определили политику, которую необходимо изменить, далее следует использовать командлет **Set-CsClientPolicy** , чтобы установить для параметра Енаблехотдескинг значение true. Например:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Кроме того, вы можете использовать командлет **New-CsClientPolicy** для создания новой политики клиента, обеспечивающей поддержку горячего рабочего стола. Например:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> После того как эта политика создана, вы должны назначить ее соответствующим телефонам. Подробности можно найти <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">в разделе назначение политик в Lync Server 2013 на общем телефоне</A>с областями.



</div>

<div>

## <a name="disabling-hot-desking"></a>Отключение поддержки горячей замены

  - Чтобы отключить функцию горячего подключения для обычного телефонного телефона, сбросьте параметр Енаблехотдескинг командлета **Set-CsClientPolicy** в значение по умолчанию, равное false. Например:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Подробные сведения можно найти в разделах справки по командлетам [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и командлету [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

