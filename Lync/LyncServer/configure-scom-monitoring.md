---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7904edf9723dacdd28f69a75bec17cb5db3c2061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Настройка мониторинга SCOM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-04_

После перехода на Microsoft Lync Server 2013 необходимо выполнить несколько задач, чтобы настроить Lync Server 2013 для работы с System Center Operations Manager.

  - Примените к серверу Lync Server 2010 обновлений, выбранных для управления логикой центрального обнаружения.

  - Обновите раздел реестра для основного сервера поиска кандидатов.

  - Настройка основного сервера System Center Operations Manager для переопределения узла центра обнаружения кандидатов.

Ниже приведены инструкции по переносу каждой из этих задач.

**Примените к серверу Lync Server 2010 обновлений, выбранных для управления логикой центрального обнаружения.**

1.  Выровняйте сервер, на котором установлены файлы агента System Center Operations Manager и настроен как узел обнаружения кандидатов.

2.  Примените к этому серверу обновления Lync Server 2010. Ознакомьтесь с разделом [применение обновлений Lync Server 2010](apply-lync-server-2010-updates.md).

**Обновите раздел реестра для основного сервера поиска кандидатов.**

1.  На сервере, выбранном для управления логикой центрального обнаружения, Откройте командное окно Windows PowerShell.

2.  В командной строке введите следующую команду:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > При внесении изменений в реестр может возникнуть сообщение о том, что команда завершилась сбоем, если раздел реестра уже существует. Если вы столкнетесь с этим, вы можете спокойно проигнорировать ошибку.

    
    </div>

**Настройка основного сервера System Center Operations Manager для переопределения узла наблюдения за центральным обнаружением.**

1.  На компьютере с установленной консолью System Center Operations Manager разверните **объект пакета управления** , а затем выберите пункт **Обнаружение объектов**.

2.  Выберите команду **изменить область...**

3.  На странице " **объекты пакета управления областью** " выберите **кандидат на обнаружение Ls**.

4.  Переопределение **действующего значения-кандидата на обнаружение Ls** на имя сервера-кандидата, выбранное в предыдущей процедуре.

Наконец, чтобы завершить изменения, перезапустите службу работоспособности на корневом сервере управления System Center Operations Manager.

</div>

<span> </span>

</div>

</div>

</div>

