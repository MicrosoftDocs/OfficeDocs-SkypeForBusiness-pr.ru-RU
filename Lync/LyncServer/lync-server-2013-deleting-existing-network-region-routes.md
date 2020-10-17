---
title: 'Lync Server 2013: удаление существующих маршрутов между сетевыми областями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07a0331563c4d78c4e8fc3391b7f8423a2ecc21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525396"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Удаление существующих маршрутов областей сети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области. Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой. Для настройки маршрутов областей сети можно использовать панель управления Lync Server. С помощью панели управления Lync Server вы можете создать, изменить или удалить маршрут области сети. С помощью инструкций, приведенных в этом разделе, можно удалить существующие маршруты сетевых регионов. Дополнительные сведения о создании или изменении маршрутов для областей сети см [в статье Создание или изменение маршрутов для областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-delete-a-network-region-route"></a>Чтобы удалить маршрут сетевого региона

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В панели навигации выберите **Настройка сети**, а затем щелкните **Маршрут региона**.

4.  На странице **Маршрут региона** щелкните маршрут, который следует удалить.
    
    <div>
    

    > [!NOTE]  
    > Одновременно можно удалить сразу несколько маршрутов регионов. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько маршрутов регионов. Или щелкните пункт <STRONG>Выделить все</STRONG> в меню <STRONG>Изменить</STRONG> для выбора сразу нескольких маршрутов.

    
    </div>

5.  В меню **Изменить** щелкните **Удалить**.

6.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение маршрутов областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[Настройка маршрута области сети](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[New — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get — Кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

