---
title: Lync Server 2013; Создание маршрутов межсетевого региона
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 9d234d959f434e9e2b96850add488ecd4eac952c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Создание маршрутов между межсетевыми регионах в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

*Маршрут к межсетевому региону* определяет маршрут между парой областей сети. Для каждой пары областей сети в развертывании средства управления допуском звонков требуется маршрут сетевого региона. Это позволяет каждому региону сети в рамках развертывания осуществлять доступ к любому другому региону.

Несмотря на то, что ссылки на области устанавливают ограничения пропускной способности для подключений между регионами, межрегионовый маршрут определяет связанный путь, по которому будет проходить соединение из одной области в другую.

Дополнительные сведения о работе с маршрутами между сетевыми контактами можно найти в документации по оболочке управления Lync Server для следующих командлетов:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

В примере топологии сетевые маршруты между регионами должны быть определены для каждой из трех пар регионов: Северная Америка/EMEA, EMEA/APAC, Северная Америка и APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Создание маршрутов межсетевого региона с помощью среды управления Lync Server

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Выполните командлет **New-CsNetworkInterRegionRoute**, чтобы определить необходимые маршруты. Например, выполните командлет:
    
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
    > Для маршрута межсетевого взаимодействия в Северной Америке и APAC требуется две ссылки на сетевой регион, так как между ними нет связи между прямыми сетевыми регионах.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Создание маршрутов межсетевого региона с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Щелкните кнопку навигации **Маршрут региона**.

4.  Выберите **Создать**.

5.  На странице **Новый маршрут** выберите **имя** , а затем введите имя для маршрута сетевого региона.

6.  Щелкните **сетевую \#область 1**, а затем щелкните в списке сетевой регион, который вы хотите перенаправить в сетевой \#регион 2.

7.  Щелкните **Сетевое \#окружение 2**, а затем щелкните в списке сетевой регион, который нужно переслать в сетевую \#область 1.

8.  Нажмите кнопку **Добавить** рядом с полем **связи по сетевому региону** , а затем добавьте ссылку на сетевой регион, которая будет использоваться в маршруте межсетевого соединения.
    
    <div class=" ">
    

    > [!NOTE]  
    > При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута. Например, для маршрута межсетевого взаимодействия в Северной Америке и APAC требуется две ссылки на сетевой регион, так как между ними нет ссылки на прямую сетевую область.

    
    </div>

9.  Нажмите **Исполнить**.

10. Чтобы завершить создание маршрутов межсетевой связи для топологии, повторите действия 4 – 9 с параметрами для других маршрутов межсетевого связи.

</div>

</div>

<span> </span>

</div>

</div>

</div>

