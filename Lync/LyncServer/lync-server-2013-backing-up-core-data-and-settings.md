---
title: 'Lync Server 2013: резервное копирование основных данных и параметров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a6614a06ea4e5370dd944940d35a690853c171b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Резервное копирование основных данных и параметров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-04-23_

В следующих процедурах используются командлеты командной консоли Lync Server для создания файлов резервных копий параметров и данных для основных служб. Дополнительные сведения о средствах, используемых в этом разделе, в том числе о том, где они находятся, приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Сведения о резервном копировании данных архивации и мониторинга приведены [в статье резервное копирование баз данных архивации и мониторинга в Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> Шаг в этом разделе для резервного копирования центрального хранилища управления включает параметры и конфигурацию для архивации и мониторинга.



</div>

Вы можете выполнить командлеты, описанные в этом разделе, локально или удаленно.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Резервное копирование основных данных и параметров

1.  Из учетной записи пользователя, входящей в группу RTCUniversalServerAdmins, войдите на любой компьютер во внутреннем развертывании.

2.  Чтобы сохранить резервные копии, созданные в следующих шагах, создайте новую общую папку и обновите путь, на который ссылается **$BACKUP** , на новую общую папку.

3.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

4.  Выполните резервное копирование файла конфигурации центрального хранилища управления. В командной строке введите следующую команду:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Пример:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > На этом этапе выполняется экспорт топологии, политик и параметров конфигурации Lync Server в файл. Для резервного копирования данных топологии не требуется никаких других действий.

    
    </div>

5.  Скопируйте файл конфигурации резервного хранилища центрального хранилища управления в $Backup\\.

6.  Резервное копирование данных службы сведений о местоположении. В командной строке введите следующую команду:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Пример:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Скопируйте файл конфигурации службы сведений о расположении резервной копии в $Backup\\.

8.  Создайте резервную копию пользовательских данных для каждой внутренней базы данных интерфейсного пула и каждого сервера Standard Edition. В командной строке введите следующую команду:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Пример:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Скопируйте резервную копию файла пользователя в $Backup\\.

10. В каждом пуле, где выполняется приложение группы ответа, создайте резервную копию конфигурации группы ответа. Выполните указанные ниже действия.
    
    1.  В командной строке введите следующую команду.
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Например:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Скопируйте файл конфигурации группы ответа с резервной копией в\\$Backup.

</div>

</div>

<span> </span>

</div>

</div>

</div>

