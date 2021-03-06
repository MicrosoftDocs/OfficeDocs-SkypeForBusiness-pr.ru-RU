﻿---
title: Просмотр сведений о маршруте областей сети
TOCTitle: Просмотр сведений о маршруте областей сети
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49887942
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр сведений о маршруте областей сети

 

_**Дата изменения раздела:** 2013-02-23_

Каждая область в конфигурации контроля допуска звонков (CAC) должна иметь возможность доступа к каждой другой области. Связи между областями налагают определенные ограничения на пропускную способность, доступную подключениям между областями, а также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой. В описанных ниже процедурах для просмотра имеющихся маршрутов между областями сети используется панель управления Lync Server 2013 или командная консоль Lync Server 2013. Подробные сведения о создании или изменении маршрутов между областями сети см. в разделе [Создание или изменение маршрутов между сетевыми областями](lync-server-2013-creating-or-modifying-network-region-routes.md).

## Просмотр информации о маршруте между областями сети — панель управления Lync Server

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации выберите **Настройка сети**, а затем щелкните **Маршрут региона**.

4.  На странице **Маршрут региона** выберите маршрут области, который хотите просмотреть.
    
    > [!NOTE]  
    > Можно просматривать только один маршрут за один раз.

5.  В меню **Изменить** щелкните **Подробнее**.

## Просмотр информации о маршруте между областями сети с помощью командлетов Lync Server PowerShell

Для просмотра информации о маршруте между областями сети можно также использовать Lync Server PowerShell и командлет Get-CsNetworkInterRegionRoute. Этот командлет можно выполнить с командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр информации о маршруте между областями сети

  - Чтобы просмотреть информацию обо всех маршрутах между областями сети, введите следующую команду на командной консоли Командная консоль Lync Server и нажмите клавишу ВВОД:
    
        Get-CsNetworkInterRegionRoute
    
    Будут возвращены сведения, аналогичные приведенным ниже:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute).

## См. также

#### Задачи

[Создание или изменение маршрутов между сетевыми областями](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Удаление существующих маршрутов областей сети](lync-server-2013-deleting-existing-network-region-routes.md)

