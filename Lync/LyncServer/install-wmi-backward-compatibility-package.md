---
title: Установка пакета обратной совместимости WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b8d474ff451a488124ebfbae0ff0872a6cca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Установка пакета обратной совместимости WMI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Если вы попытаетесь запустить мастер слияния построителя топологии без установки пакета обратной совместимости WMI, появится следующее сообщение об ошибке:

![Сообщение об ошибке WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Сообщение об ошибке WMI")

При попытке выполнить командлет **Merge-кслегацитопологи** без установки пакета обратной совместимости WMI появляется следующее сообщение об ошибке:

![Ошибка поставщика Windows PowerShell WMI](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Ошибка поставщика Windows PowerShell WMI")

Установка пакета обратной совместимости WMI

1.  С установочного \\носителя перейдите к разделу\\Настройка\\\\оксвмибк AMD64. Установщика.

2.  Установите ОКСВМИБК. Установщика.
    
    <div>
    

    > [!IMPORTANT]  
    > ОКСВМИБК. msi должен быть установлен на компьютере, на котором запущен мастер объединения Topology Builder. Тем не менее, мы рекомендуем установить ОКСВМИБК. msi на всех серверах переднего плана в вашей топологии.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > ОКСВМИБК. msi можно установить на любом компьютере домена, на котором установлены основные компоненты Lync Server 2013 и консоль управления Lync Server 2013, и у него есть доступ к топологии Office Communications Server 2007 R2 (поставщик WMI для домена Active Directory) Службы (AD DS) и SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

