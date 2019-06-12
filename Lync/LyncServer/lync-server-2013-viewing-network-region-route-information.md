---
title: 'Lync Server 2013: Просмотр сведений о маршрутах для сетевого региона'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4438a3af4a9bfbdaf88d4412b769cdaaba9d3d43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Просмотр сведений о маршруте в сетевом регионе в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Каждый регион в конфигурации управления допуском звонков (CAC) должен иметь какой-либо способ получить доступ ко всем остальным регионам. Несмотря на то, что ссылки на области устанавливают ограничения пропускной способности для подключений между регионами и представляют собой физические ссылки, маршрут определяет связанный путь, который будет проходить соединение между двумя областями. Воспользуйтесь приведенными ниже инструкциями, чтобы просмотреть существующие маршруты к сетевым областям в Lync Server 2013 панели управления или в командной консоли Lync Server 2013. Дополнительные сведения о создании и изменении маршрутов сетевого региона можно найти [в разделе Создание и изменение маршрутов сетевого региона в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Просмотр сведений о маршруте сетевого региона на панели управления Lync Server

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — пункт **путь**к региону.

4.  На странице " **регион** " щелкните маршрут области, который вы хотите просмотреть.
    
    <div>
    

    > [!NOTE]  
    > Вы можете просматривать только один маршрут области за раз.

    
    </div>

5.  В меню **Правка** щелкните **Подробнее**.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о маршруте сетевого региона с помощью командлетов Windows PowerShell

Сведения о маршруте сетевого региона можно просмотреть с помощью Windows PowerShell и командлета Get-Кснетворкинтеррегионрауте. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-network-region-route-information"></a>Просмотр сведений о маршруте сетевого региона

  - Чтобы просмотреть сведения о всех маршрутах сетевого региона, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД.
    
        Get-CsNetworkInterRegionRoute
    
    Команда возвращает примерно следующую информацию:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение маршрутов сетевого региона в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Удаление существующих маршрутов сетевого региона в Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

