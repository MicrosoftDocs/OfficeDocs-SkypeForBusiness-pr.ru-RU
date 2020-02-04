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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Резервное копирование основных данных и параметров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-04-23_

Следующие процедуры используют командлеты командной консоли Lync Server для создания резервных файлов для параметров и данных основных служб. Дополнительные сведения о средствах, используемых в этом разделе, в том числе о том, где они находятся, приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: инструменты и разрешения](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Подробнее об архивации и мониторинге данных можно найти в разделе [резервное копирование архивации и мониторинг баз данных в Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> В этом разделе описывается создание резервной копии центрального хранилища, включая параметры и конфигурацию для архивации и мониторинга.



</div>

Командлеты, описанные в этом разделе, можно выполнять локально или удаленно.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Создание резервной копии основных данных и параметров

1.  Войдите в свою учетную запись пользователя, которая входит в группу Рткуниверсалсерверадминс, на любой компьютер во внутренней среде.

2.  Чтобы сохранить резервные копии, созданные с помощью описанных ниже действий, создайте новую общую папку и обновите путь, на который ссылается **$BACKUP** , в новую общую папку.

3.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

4.  Создавайте резервную копию файла конфигурации центрального хранилища. В командной строке введите следующую команду:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Например:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > На этом этапе в файл экспортируются топология сервера Lync, политики и параметры конфигурации. Для резервного копирования данных топологии не требуется выполнять другие действия.

    
    </div>

5.  Скопируйте резервную копию файла конфигурации центрального хранилища для $Backup\\.

6.  Резервное копирование данных службы сведений о расположении. В командной строке введите следующую команду:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Например:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Скопируйте файл конфигурации службы сведений о расположении из резервной копии в\\$Backup.

8.  Создавайте резервные копии данных пользователей для каждой серверной базы данных в пуле переднего плана и на каждом стандартном сервере выпуске. В командной строке введите следующую команду:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Например:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Скопируйте резервную копию файла пользователя в $Backup\\.

10. В каждом пуле, где запущено приложение группы ответа, создавайте резервные копии конфигурации группы ответа. Выполните указанные ниже действия.
    
    1.  В командной строке введите следующую команду:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Например:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Скопируйте резервную копию файла конфигурации группы ответов в $Backup\\.

</div>

</div>

<span> </span>

</div>

</div>

</div>

