---
title: Запуск Линкперфтул
description: Запустите Линкперфтул.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560085"
---
# <a name="run-lyncperftool"></a>Запуск Линкперфтул

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-24_

Перед запуском средства нагрузки и производительности Lync Server 2013 (LyncPerfTool.exe) необходимо создать пользователей, контакты и сценарии. Сведения об использовании средств для выполнения этих действий приведены в статье [Создание пользователей и контактов](create-users-and-contacts.md) и [Настройка профиля пользователя](configure-user-profile.md). При запуске этих средств также создается файл, который будет запускаться LyncPerfTool.exe в составе пакетного файла с включенными в него необходимыми параметрами.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Запуск средства нагрузочного тестирования и производительности Lync Server 2013

Средство UserProfileGenerator.exe создает пакетный файл, который позволяет запускать LyncPerfTool.exe путем регистрации счетчиков производительности Линкперфтул и загрузки XML-файла конфигурации. Пакетный файл запускает один экземпляр LyncPerfTool.exe для каждого файла конфигурации. Чтобы запустить пакетный файл, выполните следующие действия:

1.  Скопируйте папку, содержащую папки и файлы конфигурации, в каталог, содержащий LyncStressTool.exe на каждом клиентском компьютере. (Например, если вы создали файлы конфигурации в папке с именем 1,28 \_ 13.16.16, скопируйте эту папку в папку, содержащую LyncPerfTool.exe на каждом клиенте.)

2.  Перейдите к папке клиента с соответствующим номером и запустите пакетный сценарий Рунклиент. Можно просто дважды щелкнуть пакетный файл в проводнике Windows, который будет выполнять все файлы конфигурации для этого номера клиента. Вы также можете запустить скрипт из соответствующей клиентской папки с помощью следующего синтаксиса:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Чтобы запустить LyncPerfTool.exe напрямую, откройте командную строку и введите в командной строке следующую команду (при первом запуске обязательно Зарегистрируйте счетчики производительности regsvr32/i/n/s LyncPerfToolPerf.dll, как показано в примечании далее в этой статье) :LyncPerfTool.exe/file:\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Чтобы средство отображало значения в файле конфигурации, включите в предыдущую команду параметр/дисплайфиле, как показано ниже.
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Чтобы завершить процесс, нажмите клавиши CTRL + C.

<div>


> [!NOTE]  
> Перед запуском Линкперфтул напрямую необходимо зарегистрировать счетчики производительности. Введите следующую команду, чтобы зарегистрировать счетчики производительности:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Каждый экземпляр LyncPerfTool.exe, который вы запускаете, сразу же начнет входить в систему пользователей, как правило, на частоте одного пользователя в секунду. Пиковая частота входа пользователей в пул составляет около 12 в секунду. Это означает, что не следует запускать более 12 экземпляров Линкперфтул одновременно, а пользователи по-прежнему подписываются. 1000 пользователям потребуется около 20 минут, чтобы выполнять вход по одной в секунду.



</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание пользователей и контактов](create-users-and-contacts.md)  
[Настройка профиля пользователя](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

