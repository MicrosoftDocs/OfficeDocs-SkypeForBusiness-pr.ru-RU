---
title: Установка основных файлов Lync Server 2013 и базы данных RTCLocal
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
ms.openlocfilehash: 17b3b1925607a80f143c57e6185c7a709b19ee0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Установка основных файлов Lync Server 2013 и базы данных RTCLocal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

Чтобы установить основные файлы Lync Server 2013 на компьютер, выполните следующую процедуру. База данных RTCLocal устанавливается автоматически при установке файлов основных данных. Обратите внимание, что не требуется устанавливать SQL Server на узлах-наблюдателях. Вместо этого экспресс-выпуск SQL Server устанавливается автоматически.

Установка основных файлов Lync Server 2013 и базы данных RTCLocal:

1.  На компьютере узла-наблюдателя в меню **Пуск** щелкните **Все программы**, выберите **Стандартные**, щелкните правой кнопкой мыши **Командная строка**, а затем выберите команду **Запуск от имени администратора**.

2.  В окне консоли введите следующую команду и нажмите клавишу ВВОД, указав соответствующий путь к файлам установки Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Чтобы убедиться, что основные компоненты Lync Server были успешно установлены, нажмите кнопку **Пуск**, выберите **все программы**, **Lync Server 2013**и щелкните **Lync Server Management Shell**. В консоли управления Lync Server 2013 введите следующую команду Windows PowerShell и нажмите клавишу ВВОД:

    Get-CsWatcherNodeConfiguration

При первом выполнении этой команды данные не возвращаются, так как в качестве узла-наблюдателя не настроек ни один компьютер. Если команда выполняется без возврата ошибки, можно предположить, что установка Lync Server выполнена успешно.

Если компьютер узла-наблюдателя расположен внутри сети периметра, можно выполнить следующую команду, чтобы проверить установку Lync Server 2013:

    Get-CsPinPolicy

Отобразятся данные в следующем виде в соответствии с количеством политик ПИН-кодов, настроенных для организации:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Если отображаются сведения о политиках ПИН-кодов, это означает, что основные компоненты были успешно установлены.

</div>

<span> </span>

</div>

</div>

</div>

