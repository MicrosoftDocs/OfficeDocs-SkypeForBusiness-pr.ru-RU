---
title: 'Lync Server 2013: Просмотр сведений о связи между областями сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69040594a04d71f07d004826e4207c0b23612f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535696"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Просмотр сведений о связи между областями сети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Вы можете просмотреть каналы между двумя областями сети как часть контроля допуска звонков (CAC). Регионы в сети связываются с помощью физического подключения глобальной сети. Вы можете использовать панель управления Lync Server для просмотра существующей связи между двумя областями сети. Дополнительные сведения о создании или изменении связи между областями сети содержатся [в разделе Настройка связей между областями сети в Lync Server 2013](lync-server-2013-configuring-network-region-links.md).

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Просмотр связи между областями сети в панели управления Lync Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.

4.  На странице **Канал области** щелкните канал области, который нужно просмотреть.
    
    <div>
    

    > [!NOTE]  
    > За один раз вы можете просмотреть сведения только об одном канале области.

    
    </div>

5.  В меню **Правка** щелкните пункт **Показать подробности**.

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о связи между областями сети с помощью командлетов Windows PowerShell

Вы можете просматривать связи между областями сети с помощью Windows PowerShell и командлета **Get – кснетворкрегионлинк** . Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-link-information"></a>Просмотр сведений о канале области сети

  - Чтобы просмотреть сведения о всех ссылках на область сети, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:
    
        Get-CsNetworkRegionLink
    
    Эта команда возвращает следующую информацию:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

Дополнительные сведения см. в разделе [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка связей между сетевыми сайтами в Lync Server 2013](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

