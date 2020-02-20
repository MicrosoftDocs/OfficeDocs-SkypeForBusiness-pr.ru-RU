---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae2d3b588cafb09fd2eaea821b998b546fd0211
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Перемещение каталогов конференций

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в пуле Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Перемещение каталога конференций на Lync Server 2013

1.  Откройте командную консоль Lync Server.

2.  Чтобы получить идентификатор каталогов конференций в организации, выполните следующие команды:
    
        Get-CsConferenceDirectory
    
    Так как этот командлет возвращает все каталоги конференций в организации, вы можете ограничить результаты только для ликвидируемого пула. Например, если вы хотите ликвидировать пул с полным доменным именем pool01.contoso.net, выполните следующую команду:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Этот командлет возвращает все каталоги конференций, для которых идентификатор службы содержит полное доменное имя pool01.contoso.net.

3.  Для перемещения каталогов конференций выполните следующую команду для каждого каталога конференции в пуле:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Например:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Вы можете столкнуться с ошибкой, показанной ниже, которая связана с тем, что командная консоль Lync Server запрашивает обновленный набор разрешений из Active Directory. Чтобы устранить эту ошибку, закрыло текущее окно и откройте новую командную консоль Lync Server, а затем снова запустите эту команду.



</div>

![Вывод ошибок Move – CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Вывод ошибок Move – CsConferenceDirectory")

</div>

</div>

<span> </span>

</div>

</div>

</div>

