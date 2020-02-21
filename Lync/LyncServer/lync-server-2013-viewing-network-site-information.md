---
title: 'Lync Server 2013: Просмотр сведений о сетевом сайте'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bf9f10ed66fec57516f14cf17a71692fc360da7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a>Просмотр сведений о сетевом сайте в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1. Сведения о сетевом сайте можно просматривать либо в панели управления Lync Server 2013, либо в командной консоли Lync Server. Дополнительные сведения о создании или изменении сетевых сайтов можно найти [в статье Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a>Просмотр сведений о сетевом сайте в панели управления Lync Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конфигурация сети** и выберите **Сайт**.

4.  На странице **Сайт** выберите сайт, который хотите просмотреть.
    
    <div>
    

    > [!NOTE]  
    > Допускается одновременный просмотр данных только для одного сайта.

    
    </div>

5.  В меню **Правка** щелкните **Показать подробности**.

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о сетевом сайте с помощью командлетов Windows PowerShell

Сведения о сетевом сайте можно просмотреть с помощью Windows PowerShell и командлета Get-CsNetworkSite. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-network-site-information"></a>Просмотр сведений о сетевом сайте

  - Чтобы просмотреть сведения обо всех сетевых сайтах, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsNetworkSite
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

Дополнительные сведения см. в разделе справки для командлета [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)  
[Удаление существующего сетевого сайта в Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

