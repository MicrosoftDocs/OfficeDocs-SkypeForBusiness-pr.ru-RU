---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Настройка мониторинга SCOM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

После перехода на Microsoft Lync Server 2013 необходимо выполнить несколько задач, чтобы настроить Lync Server 2013 для работы с System Center Operations Manager.

  - Применение обновлений Lync Server 2010 к серверу, выбранному для управления логикой центрального обнаружения.

  - Обновите раздел реестра потенциального сервера централизованного обнаружения.

  - Настройте основной сервер управления System Center Operations Manager, чтобы переопределить узел центра обнаружения кандидатов.

Инструкции по выполнению каждой задачи приведены ниже.

**Применение обновлений Lync Server 2010 к серверу, выбранному для управления логикой центрального обнаружения.**

1.  Выберите сервер, на котором установлены файлы агента System Center Operations Manager и который настроен как потенциальный узел обнаружения.

2.  Примените к этому серверу обновления Lync Server 2010. Ознакомьтесь с разделом [Apply The Lync Server 2010 Updates](apply-lync-server-2010-updates.md).

**Обновите раздел реестра потенциального сервера централизованного обнаружения.**

1.  На сервере, выбранном для управления логикой централизованного обнаружения, Откройте командное окно Windows PowerShell.

2.  В командной строке введите следующую команду:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > При редактировании реестра может возникнуть ошибка выполнения команды, если раздел реестра уже существует. Эту ошибку можно игнорировать.

    
    </div>

**Настройка основного сервера управления System Center Operations Manager для переопределения узла-наблюдателя центра обнаружения кандидатов.**

1.  На компьютере с установленной консолью System Center Operations Manager разверните **Объекты пакета управления** и выберите **Обнаружение объектов**.

2.  Щелкните пункт **Изменение области...**

3.  на странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.

4.  Переопределите **Эффективное значение LS Discovery Candidate**, указав имя сервера, выбранного ранее.

Наконец, чтобы завершить внесение изменений, перезапустите службу работоспособности на корневом сервере управления System Center Operations Manager.

</div>

<span> </span>

</div>

</div>

</div>

