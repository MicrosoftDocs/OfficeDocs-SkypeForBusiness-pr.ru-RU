---
title: 'Lync Server 2013: Просмотр сведений о подсети сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453d66d35d02d6b0e91f0c6b82b1ccfe71f149b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535606"
---
# <a name="viewing-network-subnet-information-in-lync-server-2013"></a>Просмотр сведений о подсети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Для просмотра сетевой подсети можно использовать следующую процедуру. С помощью панели управления Lync Server можно создавать, изменять и удалять подсеть. Дополнительные сведения о создании или изменении подсетей сети приведены [в статье Создание или изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

<div>

## <a name="to-view-a-network-subnet"></a>Чтобы просмотреть подсеть

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конфигурация сети**, затем **Подсеть**.

4.  На странице **Подсеть** щелкните подсеть, которую следует просмотреть.
    
    <div>
    

    > [!NOTE]  
    > Одновременно можно просматривать только одну подсеть.

    
    </div>

5.  В меню **Изменить** щелкните **Показать сведения**.

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации подсети с помощью командлетов Windows PowerShell

Сведения о подсети можно просмотреть с помощью Windows PowerShell и командлета Get-CsNetworkSubnet. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-subnet-information"></a>Просмотр сведений о подсети

  - Чтобы просмотреть сведения о всех сетевых подсетях, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsNetworkSubnet
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение сетевых подсетей в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
[Удаление сетевых подсетей в Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

