---
title: 'Lync Server 2013: Удаление группы агентов'
description: 'Lync Server 2013: Удаление группы агентов.'
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
ms.openlocfilehash: dded2db0957e37a624d7e8bf3a06e102f8d35cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553685"
---
# <a name="delete-an-agent-group-in-lync-server-2013"></a>Удаление группы агентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Воспользуйтесь одной из описанных ниже процедур, чтобы удалить группу агентов.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a>Удаление группы агентов с помощью панели управления Lync Server

1.  Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Response Groups** (Группы ответа), а затем **Group** (Группа).

4.  На странице  **Response Groups** (Группы ответа) в поле поиска введите полностью или частично имя группы агентов, которую вы хотите удалить.

5.  В списке результатов поиска выберите требуемую группу, нажмите кнопку **Изменить**, а затем щелкните элемент **Удалить**.

6.  Click **ОК**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a>Удаление группы агентов с помощью Windows PowerShell

1.  Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните следующую команду:
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    Пример:
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение группы агентов в Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)  


[Remove — CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get — CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

