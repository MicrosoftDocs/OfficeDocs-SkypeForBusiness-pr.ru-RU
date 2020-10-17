---
title: Перемещение каталогов конференций Lync Server 2010 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d1a080f7183bbab62cae679c911c76261694406
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500276"
---
# <a name="move-conference-directories"></a>Перемещение каталогов конференций

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-28_

Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в пуле Lync Server 2010.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Перемещение каталога конференций на Lync Server 2013

1.  Откройте командную консоль Lync Server.

2.  Чтобы получить удостоверение каталогов конференций в Организации, выполните следующую команду:
    
        Get-CsConferenceDirectory
    
    Предыдущая команда возвращает все каталоги конференций в Организации. Из-за этого может потребоваться ограничить результаты для пула, который будет списан. Например, при списании пула с полным доменным именем (FQDN) pool01.contoso.net используйте следующую команду, чтобы ограничить возвращаемые данные каталогами конференций из этого пула:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Эта команда возвращает только каталоги конференций, в которых свойство ServiceID содержит полное доменное имя pool01.contoso.net.

3.  Чтобы переместить каталоги конференций, выполните следующую команду для каждого каталога конференции в пуле:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Например, чтобы переместить каталог конференции 3, используйте эту команду, указав пул Lync Server 2013 в качестве TargetPool:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Если вы хотите переместить все каталоги конференций в пуле, используйте команду, аналогичную следующей:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Ознакомьтесь с документом "удаление Microsoft Lync Server 2010 и удаление ролей сервера" (которые можно скачать [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) ) для получения исчерпывающих пошаговых инструкций по списанию пулов Lync 2010.

При перемещении каталогов конференций может возникнуть следующая ошибка:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Эта ошибка обычно возникает, если для выполнения задачи в командной консоли Lync Server требуется обновленный набор разрешений Active Directory. Чтобы устранить эту проблему, закройте текущий экземпляр командной консоли, а затем откройте новый экземпляр командной консоли и повторно выполните команду, чтобы переместить каталог конференции.

</div>

</div>

<span> </span>

</div>

</div>

</div>

