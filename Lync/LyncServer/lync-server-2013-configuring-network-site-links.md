---
title: 'Lync Server 2013: Настройка ссылок на сайты сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Настройка связей сайтов сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

В конфигурации управления допуском звонков (CAC) можно создавать сетевые политики межсайтовых связей, определяющие ограничения пропускной способности между сайтами, которые непосредственно связаны. Если сетевые сайты имеют прямую связь, для них можно определять ограничения пропускной способности для аудио-и видеоподключений. Вы не можете использовать панель управления Lync Server для настройки политик сетевого сайта, это можно сделать только с помощью командлетов из командной консоли Lync Server Management Shell. Вы можете создавать, изменять и удалять ссылки на сетевые сайты (также называемые межсетевой политикой сайтов) из командной консоли Lync Server Management Shell.

<div>

## <a name="to-create-a-network-site-link"></a>Создание связи сайтов сети

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке введите следующую команду: подставляемые значения, которые являются допустимыми для вашей конфигурации.
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    В этом примере создается ссылка на веб-сайт с\_именем Рено Портленде, которая устанавливает ограничения для пропускной способности между сайтами Рено и Портленде. Перед выполнением этой команды необходимо, чтобы сетевые сайты и профиль политики пропускания уже существовали.

Подробное описание параметров можно найти в разделе [New-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server. Чтобы получить список профилей политики пропускной способности, которые можно применить к связи сайтов сети, вызовите командлет **Get-кснетворкбандвидсполиципрофиле** . Подробности можно найти в разделе [Get-кснетворкбандвидсполиципрофиле](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) в документации по среде управления Lync Server.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Изменение связи сайтов сети

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Используйте командлет **Set-кснетворкинтерситеполици** , чтобы изменить свойства данной ссылки на сайт сети. Вы можете изменить либо (или и то, и другое) подключенные сайты, а также изменить профиль политики для пропускной способности, связанный со ссылкой. Ниже приведен пример изменения профиля политики пропускной способности для ссылки на сайт с именем\_Рено Портленде.
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Подробное описание параметров можно найти в разделе [Set-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Удаление ссылки на сайт сети

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  С помощью командлета **Remove-кснетворкинтерситеполици** удалите связь с сетевым сайтом. В следующем примере удаляется ссылка\_на веб-сайт Рено в Портленде:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Подробное описание параметров приведено в разделе [Remove-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) в документации по среде управления Lync Server.

</div>

<div>

## <a name="see-also"></a>См. также


[Командлеты управления допуском звонков в Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

