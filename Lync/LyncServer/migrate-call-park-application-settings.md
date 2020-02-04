---
title: Перенос параметров приложения приостановки звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba55ec7ff54858d3324df2ab8794176a5dc7a10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Перенос параметров приложения приостановки звонков

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

Миграция приложения на приостановку работы из Lync Server 2010 в Lync Server 2013 включает подготовку пула Lync Server 2013 со всеми пользовательскими музыкальными файлами, загруженными в Lync Server 2010, восстановлением параметров уровня обслуживания и нацеливания на них все орбиты на всех оборотах в пул Lync Server 2013. Если настроенные файлы на удержании с хранением сконфигурированы в пуле Lync Server 2010, эти файлы необходимо скопировать в новый пул Lync Server 2013. Кроме того, рекомендуется создать резервную копию всех настроенных файлов для сохранения музыки на месте из Lync Server 2010 в другую папку назначения, чтобы сохранить отдельные резервные копии всех настроенных музыкальных файлов, которые были переданы на приостановку звонков. Настроенные на хранение музыкальные файлы для приложения для приостановки звонков хранятся в хранилище файлов пула. Чтобы скопировать звуковые файлы из хранилища файлов пула Lync Server 2010 в хранилище файлов Lync Server 2013, используйте команду **xcopy** со следующими параметрами:

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

После того как все настроенные аудиофайлы будут скопированы в хранилище файлов Lync Server 2013, должны быть настроены параметры приложения парковки для пула Lync Server 2013 и диапазоны на орбите, связанные с пулом Lync Server 2010, для которого нужно переназначить пул Lync Server 2013.

Параметры приложения для приема звонков включают пороговое значение тайм-аута отправки, включение или отключение музыки на удержании, максимальное количество попыток раскладки звонков и запрос времени ожидания. Чтобы запустить командлет **Set-кскпсконфигуратион** , необходимо управлять параметрами приложения на приостановке звонков с помощью командной консоли Lync Server. Вы не можете управлять параметрами приложения на приостановке звонков с помощью панели управления Lync Server.

**Изменение параметров службы "Приостановка звонка"**

1.  На сервере переднего плана Lync Server 2013 откройте командную консоль Lync Server Management Shell.

2.  В командной строке введите следующую команду:
    
    <div>
    

    > [!NOTE]  
    > Если параметры приложения для прикрепления звонков в Lync Server 2013 идентичны параметрам устаревшего сервера Lync Server 2010, вы можете пропустить выполнение этого действия. Если параметры приложения приостановки для Lync Server 2013 и Lync Server 2010 отличаются, для обновления этих изменений используйте командлет ниже в качестве шаблона.

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

Чтобы переназначить все диапазоны орбиты на приостановку, из пула Lync Server 2010 в пул Lync Server 2013, вы можете использовать либо панель управления Lync Server, либо консоль управления Lync Server.

**Переназначение всех диапазонов на орбиту на приостановку работы с помощью панели управления Lync Server**

1.  Откройте Панель управления Lync Server.

2.  В левой области выберите пункт **функции голосовой связи**.

3.  Откройте вкладку " **приостановить Звонок** ".

4.  Для каждого диапазона на расстоянии по орбите, назначенного для пула Lync Server 2010, измените **полное доменное имя** в параметрах конечного сервера и выберите пул Lync Server 2013, который будет обрабатывать запросы на остановку звонков.

5.  Нажмите **кнопку Сохранить,** чтобы сохранить изменения.

**Переназначение всех диапазонов на орбиту на приостановку работы с помощью командной консоли Lync Server Management Shell**

1.  Откройте командную консоль Lync Server.

2.  В командной строке введите следующую команду:
    
        Get-CsCallParkOrbit
    
    Этот командлет выводит список всех диапазонов орбиты на вкладке "приостановить". Все орбиты, в которых параметры **каллпарксервицеид** и **каллпарксерверфкдн** устанавливаются в качестве пула Lync Server 2010, должны быть переназначены.
    
    Чтобы переназначить диапазоны орбиты для сервера Lync Server 2010 в пул Lync Server 2013, в командной строке введите следующую команду:
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

После того как переназначить все диапазоны орбиты на приостановку звонков в пул Lync Server 2013, процесс миграции для приложения парковки на приостановке будет завершен, а пул Lync Server 2013 будет обрабатывать все будущие запросы на приостановку звонков.

</div>

<span> </span>

</div>

</div>

</div>

