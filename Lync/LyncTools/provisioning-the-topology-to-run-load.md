---
title: Подготовка топологии для запуска загрузки
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
ms.openlocfilehash: 6a913dc678b2f5e929ad22e09e1d8350f667ce39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Подготовка топологии для запуска загрузки

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Подготовка топологии для запуска загрузки

В зависимости от имеющихся параметров и конфигурации Lync Server 2013 в среде может потребоваться внести следующие изменения:

1.  Присвойте политике выполнения Windows PowerShell неограниченный доступ. Чтобы проверить параметры политики выполнения, откройте консоль управления Lync Server и выполните следующую команду:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Если эта команда не возвращает значение Unrestricted, выполните следующую команду:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Чтобы эффективно настроить Lync Server 2013, выполните следующие действия:
    
      - Знакомство с топологией Lync Server 2013 (например, именами компьютеров, экземплярами служб, именами сайтов и политиками).
    
      - Назначьте некоторые пользователи, созданные для групп, например группы слежения группы ответа (например, URI SIP).

3.  Чтобы запустить скрипт из командной строки, можно использовать:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  Как правило, после выполнения одного из сценариев в этом пакете результаты трассировки из сценария будут храниться в файле, который был вызван с помощью сценария с именем \<имя_сценария\>$h $ m $ s. txt. Пример: запуск ArchivingPolicy. ps1 в 12:15 P.M. создаст файл журнала, например ArchivingPolicy121500. txt.

5.  Наконец, обратите внимание, что хотя мы предоставили примеры для настройки сервера, вы несете ответственность за изменение или удаление конфигурации после завершения загрузки.

</div>

</div>

<span> </span>

</div>

</div>

</div>

