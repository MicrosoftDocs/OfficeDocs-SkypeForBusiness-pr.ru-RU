---
title: 'Lync Server 2013: Удаление группы агента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb8ebde61d1ba59952741bffd14e29ae87d482f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a>Удаление группы агента в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Для удаления группы агента воспользуйтесь одной из описанных ниже процедур.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a>Удаление группы агента с помощью панели управления Lync Server

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните **Группы ответа**, затем **Группа**.

4.  На странице **группы ответа** введите имя или часть имени группы агента, которую вы хотите удалить, в поле поиска.

5.  В списке результатов выберите группу, которую вы хотите удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.

6.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a>Использование Windows PowerShell для удаления группы агента

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке выполните следующую команду:
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    Например:
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение группы агента в Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)  


[Remove-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

