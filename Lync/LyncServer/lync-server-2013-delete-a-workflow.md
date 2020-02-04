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
ms.openlocfilehash: 4ed32780e23cce82027271e74a89fb87e194cc4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Удаление рабочего процесса в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Для удаления рабочего процесса воспользуйтесь одной из описанных ниже процедур.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Удаление рабочего процесса с помощью панели управления Lync Server

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните **Группы ответа**, затем **Рабочий процесс**.

4.  На странице **Рабочий процесс** щелкните **Создать или редактировать рабочий процесс**.

5.  В поле **выберите Поиск службы** введите часть или все имя службы **аппликатионсервер** , в которой размещен рабочий процесс, который вы хотите удалить.

6.  В списке служб выберите нужную службу и нажмите кнопку **ОК**.
    
    <div>
    

    > [!NOTE]  
    > Откроется веб-страница средства настройки группы ответа. Вы также можете открыть веб-страницу средства настройки группы ответа непосредственно из браузера, подключившись к <STRONG>&lt;HTTPS://вебпулфкдн&gt;/ргсконфиг</STRONG>.

    
    </div>

7.  В разделе **Управление существующим рабочим процессом**найдите рабочий процесс, который вы хотите удалить, а затем в разделе **действие**нажмите кнопку **Удалить**.

8.  Нажмите **Да**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Использование Windows PowerShell для удаления рабочего процесса

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке выполните следующую команду:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Например:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

