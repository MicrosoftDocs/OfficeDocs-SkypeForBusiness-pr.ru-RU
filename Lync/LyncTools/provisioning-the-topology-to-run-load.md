---
title: Подготовка топологии для загрузки
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Подготовка топологии для загрузки

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Подготовка топологии для загрузки

В зависимости от существующих настроек и конфигурации Lync Server 2013, возможно, потребуется внести в среду следующие изменения:

1.  Установите для политики выполнения Windows PowerShell неограниченный доступ. Чтобы проверить параметры политики выполнения, откройте командную консоль Lync Server Management Shell и выполните следующую команду:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Если эта команда не возвращает значение Unrestricted, выполните следующую команду:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Чтобы эффективно настроить Lync Server 2013, необходимо выполнить следующие действия.
    
      - Знакомство с топологией Lync Server 2013 (например, именами компьютеров, экземплярами служб, именами сайтов и политиками).
    
      - Назначьте пользователей, которые были созданы для групп, например группы слежения группы ответа (например, URI SIP).

3.  Чтобы запустить сценарий из командной строки, можно использовать:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  Как правило, после выполнения одного из сценариев в этом пакете результаты трассировки из сценария будут храниться в файле, расположенном в том же пути, из которого был вызван сценарий, именуемым \<\>$h $ m $ s. txt. Например, при запуске Арчивингполици. ps1 в 12:15 P.M. создаст файл журнала, например ArchivingPolicy121500. txt.

5.  Наконец, обратите внимание на то, что, несмотря на то, что мы предоставили примеры для настройки сервера, вы несете ответственность за изменение или удаление конфигурации после завершения загрузки.

</div>

</div>

<span> </span>

</div>

</div>

</div>

