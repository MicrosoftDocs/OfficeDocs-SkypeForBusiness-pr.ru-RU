---
title: 'Lync Server 2013: удаление извещения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66d10f53f89690a25860ba403ed7a8b21f7a1d4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a>Удаление объявления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Используйте следующую процедуру для удаления оповещения о вызовах на неназначенные номера.

<div>

## <a name="to-delete-an-announcement"></a>Порядок удаления оповещения

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:
    
        Get-CsAnnouncement

4.  В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    Пример:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > Дополнительные сведения о параметрах: <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get – ксаннаунцемент</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove — ксаннаунцемент</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание извещения в Lync Server 2013](lync-server-2013-create-an-announcement.md)  


[Remove — Ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[Get — Ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

