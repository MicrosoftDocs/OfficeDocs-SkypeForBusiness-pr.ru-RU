---
title: 'Lync Server 2013: Просмотр сведений о сетевом сайте'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 788440d02a3f41198a870f8419cece4dc8e66900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a>Просмотр сведений о сетевом сайте в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Сетевые сайты — это офисы или места, настроенные в каждом регионе управления допуском звонков (CAC) или Улучшенное развертывание 9-1-1. Вы можете просматривать сведения о сетевом сайте либо на панели управления Lync Server 2013, либо в командной консоли Lync Server Management Shell. Дополнительные сведения о создании и изменении сайтов сети можно найти [в разделе Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a>Просмотр сведений о сетевом сайте на панели управления Lync Server

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **сайт**.

4.  На странице **сайта** выберите сайт, который вы хотите просмотреть.
    
    <div>
    

    > [!NOTE]  
    > Вы можете просматривать сведения только для одного сайта одновременно.

    
    </div>

5.  В меню **Правка** щелкните **Подробнее**.

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о сетевом сайте с помощью командлетов Windows PowerShell

Вы можете просматривать сведения о сетевом сайте с помощью Windows PowerShell и командлета Get-Кснетворксите. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-network-site-information"></a>Просмотр сведений о сетевом сайте

  - Чтобы просмотреть сведения о всех сетевых сайтах, введите в командной консоли Lync Server указанную ниже команду и нажмите клавишу ВВОД.
    
        Get-CsNetworkSite
    
    Команда возвращает примерно следующую информацию:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворксите](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)  
[Удаление существующего сетевого сайта в Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

