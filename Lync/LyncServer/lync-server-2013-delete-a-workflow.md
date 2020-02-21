---
title: 'Lync Server 2013: Удаление рабочего процесса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f3265591b1beb7180864b8e3a613989dfca397
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Удаление рабочего процесса в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Для удаления рабочего процесса воспользуйтесь одной из следующих процедур.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Удаление рабочего процесса с помощью панели управления Lync Server

1.  Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Response Groups** (Группы ответа), а затем **Workflow** (Рабочий процесс).

4.  На странице **Workflow** (Рабочий процесс) щелкните **Create or edit a workflow** (Создание или изменение рабочего процесса).

5.  В поле поиска **Выбрать услугу** введите часть имени или полное имя службы **ApplicationServer**, где размещается рабочий процесс, который нужно удалить.

6.  В списке найденных служб выберите нужную и нажмите кнопку **ОК**.
    
    <div>
    

    > [!NOTE]  
    > Откроется веб-страница средства настройки группы ответа. Вы также можете открыть веб-страницу средства настройки группы ответа непосредственно из веб-браузера, подключившись к <STRONG>https://&lt;вебпулфкдн&gt;/ргсконфиг</STRONG>.

    
    </div>

7.  В окне **Управление существующим рабочим процессом** найдите рабочий процесс, который нужно удалить, а затем в разделе **Действие** нажмите кнопку **Удалить**.

8.  Нажмите кнопку **Да**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Использование Windows PowerShell для удаления рабочего процесса

1.  Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните следующую команду:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Пример:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

