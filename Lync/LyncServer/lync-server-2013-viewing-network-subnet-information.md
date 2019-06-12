---
title: 'Lync Server 2013: Просмотр сведений о сетевой подсети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a157746e40de8f4793fab24e7e91121779d7602e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a>Просмотр сведений о сетевой подсети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете использовать описанную ниже процедуру для просмотра сетевой подсети. С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые подсети. Дополнительные сведения о создании и изменении подсетей сети можно найти [в разделе Создание или изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

<div>

## <a name="to-view-a-network-subnet"></a>Просмотр сетевой подсети

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **подсеть**.

4.  На странице **Subnet** (подсеть) выберите подсеть, которую вы хотите просмотреть.
    
    <div>
    

    > [!NOTE]  
    > Вы можете просматривать только одну подсеть за один раз.

    
    </div>

5.  В меню **Правка** выберите пункт **Показать подробности..**..

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации сетевой подсети с помощью командлетов Windows PowerShell

Сведения о сетевой подсети можно просмотреть с помощью Windows PowerShell и командлета Get-Кснетворксубнет. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-network-subnet-information"></a>Просмотр сведений о сетевой подсети

  - Чтобы просмотреть сведения о всех подсетях, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД.
    
        Get-CsNetworkSubnet
    
    Команда возвращает примерно следующую информацию:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
[Удаление подсетей сети в Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

