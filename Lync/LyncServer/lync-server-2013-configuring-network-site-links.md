---
title: 'Lync Server 2013: Настройка связей между сетевыми сайтами'
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
ms.openlocfilehash: ccd6a4efa271a5ca70a81eb6f375ffee4d1ae45d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Настройка связей между сетевыми сайтами в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

В конфигурации контроля допуска звонков можно создать сетевые межузловые политики, которые определяют ограничения пропускной способности между связанными напрямую узлами. Когда сетевые узлы совместно используют прямую связь, ограничения для аудио- и видеосвязи можно задавать между этими двумя узлами. Вы не можете использовать панель управления Lync Server для настройки политик сетевых сайтов, это можно сделать только с помощью командлетов из командной консоли Lync Server. С помощью командной консоли Lync Server можно создавать, изменять и удалять сетевые связи сайтов (также называемые сетевой политикой межсайтовой связи).

<div>

## <a name="to-create-a-network-site-link"></a>Создание связи между сетевыми узлами

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В Введите в командной строке следующую команду, подставив значения, подходящие для вашей конфигурации:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    В этом примере создается сетевое подключение к сетевому\_сайту с именем Рино Портленде, которое задает ограничения пропускной способности между узлами Рино и сети Портленде. Перед выполнением этой команды уже должны существовать эти сетевые узлы и профиль политики пропускной способности.

Подробное описание параметров приведено в разделе [New – CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server. Чтобы получить список профилей политик пропускной способности, которые можно применять к связи между сетевыми узлами, вызовите командлет **Get-CsNetworkBandwidthPolicyProfile**. Дополнительные сведения см. в статье [Get – CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) в документации по консоли управления Lync Server.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Изменение связи между сетевыми узлами

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Для изменения свойств конкретной связи между сетевыми узлами используется командлет **Set-CsNetworkInterSitePolicy**. Можно изменять каждый из связанных узлов (или оба этих узла), а также профиль политики пропускной способности, привязанный к этой связи. Ниже приведен пример изменения профиля политики пропускной способности для связи сайтов с именем Рино\_Портленде:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Подробное описание параметров приведено в разделе [Set – CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Удаление связи между сетевыми узлами

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Для удаления связи между сетевыми узлами используется командлет **Remove-CsNetworkInterSitePolicy**. В следующем примере удаляется ссылка\_на сетевой сайт Рино в Портленде:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Подробное описание параметров приведено в разделе [Remove – CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.

</div>

<div>

## <a name="see-also"></a>См. также


[Командлеты контроля допуска звонков в Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New — CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set — CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove — CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get — CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get — CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

