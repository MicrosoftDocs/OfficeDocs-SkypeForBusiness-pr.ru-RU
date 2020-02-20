---
title: Lync Server 2013; Создание маршрутов между межсетевыми областями
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 4ab490479e02e92811878a9125c7b318732eeb83
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Создание маршрутов между межсетевыми областями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

*Маршрут между регионами сети* определяет маршрут между парой регионов сети. Маршрут между регионами сети требуется для каждой пары регионов сети в развертывании службы контроля допуска звонков. Это позволяет каждому региону сети в рамках развертывания осуществлять доступ к любому другому региону.

Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между регионами; маршруты же определяют путь, который должны пройти подключения от одного региона до другого.

Для получения подробных сведений о работе с маршрутами между сетевыми областями обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [New — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

В этом примере топологии необходимо определить маршруты между регионами сети для каждой пары регионов из трех: Северная Америка/EMEA, APAC/EMEA и APAC/Северная Америка.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Создание маршрутов между сетевыми областями с помощью командной консоли Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет **New-CsNetworkInterRegionRoute**, чтобы определить необходимые маршруты. Например, выполните:
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Для маршрута между регионами «Северная Америка/APAC» требуются две связи между регионами сети, поскольку прямая сетевая связь между этими регионами отсутствует.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Создание маршрутов между сетевыми областями с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  На левой панели навигации щелкните **Конфигурация сети**.

3.  Щелкните кнопку навигации **Маршрут региона**.

4.  Щелкните **Создать**.

5.  На странице **Новый маршрут региона** щелкните **Имя**, а затем введите имя для маршрута между регионами сети.

6.  Щелкните **область \#сети 1**, а затем выберите в списке область сети, которую нужно маршрутизировать в область \#сети 2.

7.  Щелкните **область \#сети 2**, а затем выберите в списке область сети, которую нужно перенаправить в область \#сети 1.

8.  Щелкните **Добавить** рядом с полем **Связи между регионами сети**, а затем добавьте связь с регионом сети, которая будет использоваться в маршруте между регионами сети.
    
    <div class=" ">
    

    > [!NOTE]  
    > При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута. Например, для создания маршрута между регионами сети «Северная Америка» и «APAC» требуются две связи между сетевыми регионами, так как между ними отсутствует прямая связь.

    
    </div>

9.  Щелкните **Исполнить**.

10. Чтобы завершить создание маршрутов между регионами сети, повторите шаги с 4 по 9 с указанием настроек для других маршрутов между сетевыми регионами.

</div>

</div>

<span> </span>

</div>

</div>

</div>

