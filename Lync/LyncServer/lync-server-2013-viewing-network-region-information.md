---
title: 'Lync Server 2013: Просмотр сведений о области сети'
description: 'Lync Server 2013: Просмотр сведений о области сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225cafc392b9b9d0c23f3882d530ad6d2b59f165
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565375"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a>Просмотр сведений о области сети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Область сети связывает части сети, расположенные в различных географических районах. Каждый регион сети должен быть связан с центральным сайтом. Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков. Для просмотра областей сети можно использовать панель управления Lync Server. Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений. Используйте этот раздел для просмотра существующих областей сети. Сведения о создании или изменении существующих областей сети приведены в статье [Создание или изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Просмотр сведений о области сети с помощью панели управления Lync Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конфигурация сети**, затем **Регион**.

4.  На странице **Регион** щелкните регион, который следует просмотреть.
    
    <div>
    

    > [!NOTE]  
    > одновременно можно просматривать только один регион.

    
    </div>

5.  В меню **Изменить** щелкните **Показать сведения**.

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о области сети с помощью командлетов Windows PowerShell

Сведения о области сети можно просмотреть с помощью Windows PowerShell и командлета **Get – CsNetworkRegion** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-information"></a>Просмотр сведений о области сети

  - Чтобы просмотреть сведения обо всех регионах сети, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:
    
        Get-CsNetworkRegion
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
[Удаление существующих областей сети в Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

