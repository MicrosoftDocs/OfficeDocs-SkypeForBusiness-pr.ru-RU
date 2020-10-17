---
title: 'Lync Server 2013: удаление очереди группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Response Group queue
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48184356
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c768edeff7facc1030b414d0e0e54e3516abe52
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525626"
---
# <a name="delete-a-response-group-queue-in-lync-server-2013"></a>Удаление очереди группы ответа в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Используйте одну из следующих процедур для удаления очереди.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a>Удаление очереди с помощью панели управления Lync Server

1.  Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Группы ответа** и щелкните **Очередь**.

4.  В поле поиска введите имя очереди, которую вы хотите удалить, или его часть.

5.  В списке очередей выберите нужную очередь, нажмите кнопку **Изменить**, а затем щелкните **Удалить**.

6.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a>Использование Windows PowerShell для удаления очереди

1.  Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните следующую команду:
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    Пример:
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

