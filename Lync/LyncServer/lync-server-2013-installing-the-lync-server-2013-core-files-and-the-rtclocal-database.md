---
title: Установка основных файлов Lync Server 2013 и базы данных Ртклокал
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8f0dd1fb83c595ed444a487d0321c571a09315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Установка основных файлов Lync Server 2013 и базы данных Ртклокал

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Чтобы установить основные файлы Lync Server 2013 на компьютере, выполните указанные ниже действия. База данных Ртклокал устанавливается автоматически при установке основных файлов. Обратите внимание, что вам не нужно устанавливать SQL Server на узлах наблюдения. Вместо этого SQL Server Express устанавливается автоматически.

Чтобы установить основные файлы Lync Server 2013 и базу данных Ртклокал, выполните указанные ниже действия.

1.  На компьютере с узлом-наблюдателем нажмите кнопку **Пуск**, **выберите все программы**, затем **стандартные**, щелкните правой кнопкой мыши **Командная строка**и выберите пункт **Запуск от имени администратора**.

2.  В окне консоли введите указанную ниже команду и нажмите клавишу ВВОД, указав соответствующий путь к файлам установки Lync Server.
    
        D:\Setup.exe /BootstrapLocalMgmt

Чтобы убедиться в том, что основные компоненты Lync Server были успешно установлены, нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**. В командной консоли Lync Server 2013 введите следующую команду Windows PowerShell и нажмите клавишу ВВОД:

    Get-CsWatcherNodeConfiguration

При первом запуске этой команды данные не возвращаются, так как вы еще не настроили ни один из узлов-наблюдателей. Если команда выполняется без возврата ошибки, вы можете предположить, что настройка сервера Lync Server выполнена успешно.

Если ваш компьютер-наблюдатель находится внутри сети периметра, вы можете выполнить следующую команду для проверки установки Lync Server 2013:

    Get-CsPinPolicy

В зависимости от количества политик, настроенных для использования в вашей организации, вам будут выводиться такие сведения, как, например, указанные ниже.

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Если вы видите сведения о политиках PIN-кода, это означает, что вы успешно установили основные компоненты.

</div>

<span> </span>

</div>

</div>

</div>

