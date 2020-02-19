---
title: 'Lync Server 2013: Просмотр сведений о маршруте областей сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb8d163dadafaf8824307bd784bea4670757cd87
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Просмотр сведений о маршруте области сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области. Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой. Используйте следующие процедуры для просмотра существующих маршрутов областей сети в панели управления Lync Server 2013 или консоли управления Lync Server 2013. Дополнительные сведения о создании или изменении маршрутов для областей сети см [в статье Создание или изменение маршрутов для областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Просмотр сведений о маршруте области сети в панели управления Lync Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации выберите **Настройка сети**, а затем щелкните **Маршрут региона**.

4.  На странице **Маршрут региона** выберите маршрут области, который хотите просмотреть.
    
    <div>
    

    > [!NOTE]  
    > Можно просматривать только один маршрут за один раз.

    
    </div>

5.  В меню **Изменить** щелкните **Подробнее**.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о маршруте между областями сети с помощью командлетов Windows PowerShell

Сведения о маршруте области сети можно просмотреть с помощью Windows PowerShell и командлета Get – Кснетворкинтеррегионрауте. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-network-region-route-information"></a>Просмотр сведений о маршруте между областями сети

  - Чтобы просмотреть сведения о всех маршрутах областей сети, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:
    
        Get-CsNetworkInterRegionRoute
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение маршрутов областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Удаление существующих маршрутов областей сети в Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

