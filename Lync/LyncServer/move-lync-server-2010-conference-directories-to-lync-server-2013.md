---
title: Перемещение каталогов конференций Lync Server 2010 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa32bb5be86d72d4f18d11bb85d5ce0b57a96725
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Перемещение каталогов конференций

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-28_

Перед списанием пула необходимо выполнить описанные ниже действия для каждой из каталогов конференций в пуле Lync Server 2010.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Перемещение каталога конференций на Lync Server 2013

1.  Откройте командную консоль Lync Server Management Shell.

2.  Чтобы получить удостоверение каталогов конференции в Организации, выполните следующую команду:
    
        Get-CsConferenceDirectory
    
    Предыдущая команда возвращает все каталоги конференций в Организации. По этой причине вам может потребоваться ограничить результаты для пула. Например, если вы собираетесь списать пул с полным доменным именем (FQDN) pool01.contoso.net, используйте эту команду, чтобы ограничить возвращаемые данные каталогам конференций из этого пула.
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Эта команда возвращает только каталоги конференций, в которых свойство Сервицеид имеет полное доменное имя (FQDN) pool01.contoso.net.

3.  Чтобы переместить каталоги конференций, выполните для каждой из каталогов конференций в пуле следующую команду:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Например, чтобы переместить каталог конференции 3, используйте эту команду, указав в качестве Таржетпул пул Lync Server 2013:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Если вы хотите переместить все каталоги конференций в пуле, выполните следующую команду:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Ознакомьтесь со статьей "удаление Microsoft Lync Server 2010 и отключение серверных ролей" (которую можно скачать из [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) для получения подробных пошаговых инструкций по списанию пулов Lync 2010.

При перемещении каталогов конференций может возникнуть следующая ошибка:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Как правило, эта ошибка возникает, когда для выполнения задачи в командной консоли Lync Server Management Shell требуется обновленный набор разрешений Active Directory. Чтобы устранить эту проблему, закройте текущий экземпляр интерпретатора команд, а затем откройте новый экземпляр оболочки и повторно выполните команду, чтобы переместить каталог конференций.

</div>

</div>

<span> </span>

</div>

</div>

</div>

