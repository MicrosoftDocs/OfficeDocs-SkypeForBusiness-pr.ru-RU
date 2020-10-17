---
title: 'Lync Server 2013: Удаление диапазона номеров для группового ответа на звонки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de031dd73f5fe74ba6d343cdea5414fa15988f2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525656"
---
# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a>Удаление диапазона номеров для группового ответа на звонки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Используйте следующую процедуру для удаления диапазона номеров для группового ответа на звонки.

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a>Удаление диапазона номеров группы ответа на звонки

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите следующую команду.
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    Пример:
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > Дополнительные сведения о параметрах см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove – CsCallParkOrbit</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[Remove — CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get — CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

