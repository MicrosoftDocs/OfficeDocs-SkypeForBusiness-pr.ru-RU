---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Перемещение каталогов конференций

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-04_

Перед списанием пула вам потребуется выполнить описанные ниже действия для каждой из каталогов конференций в пуле Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Перемещение каталога конференций на Lync Server 2013

1.  Откройте командную консоль Lync Server Management Shell.

2.  Чтобы получить удостоверение каталогов конференции в Организации, выполните следующие команды:
    
        Get-CsConferenceDirectory
    
    Поскольку этот командлет возвращает все каталоги конференций в Организации, может потребоваться ограничить результаты только тем пулом, для которого вы хотите списать. Например, если вы хотите списать пул с полным доменным именем (FQDN) pool01.contoso.net, выполните указанные ниже действия.
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Этот командлет возвращает все каталоги конференций, в которых служба Service ID имеет полное доменное имя (FQDN) pool01.contoso.net.

3.  Чтобы переместить каталоги конференций, выполните указанные ниже действия для каждой из каталогов конференций в пуле.
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Например:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Вы можете столкнуться с ошибкой, описанной ниже, которая связана с тем, что в командной консоли Lync Server, требующей обновленный набор разрешений из Active Directory. Чтобы устранить эту ошибку, закройте текущее окно и откройте новую консоль управления Lync Server, а затем выполните команду еще раз.



</div>

![Вывод ошибок Move-ксконференцедиректори] (images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Вывод ошибок Move-ксконференцедиректори")

</div>

</div>

<span> </span>

</div>

</div>

</div>

