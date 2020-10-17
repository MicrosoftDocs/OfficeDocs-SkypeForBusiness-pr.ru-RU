---
title: Установка пакета обратной совместимости WMI
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655d72b2362c6b31d6fc15fd3af0ec14716b13c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523366"
---
# <a name="install-wmi-backward-compatibility-package"></a>Установка пакета обратной совместимости WMI

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Если попытаться запустить мастер объединения построителя топологий без установки пакета обратной совместимости WMI, появится следующая ошибка.

![Сообщение об ошибке WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Сообщение об ошибке WMI")

Если попытаться запустить командлет **Merge-CsLegacytopology** без установки пакета обратной совместимости WMI, появится следующая ошибка.

![Ошибка поставщика WMI Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Ошибка поставщика WMI Windows PowerShell")

Чтобы установить пакет обратной совместимости WMI, выполните следующие действия.

1.  На установочном носителе перейдите в раздел \\ настройка \\ \\OCSWMIBC.MSI установки amd64 \\ .

2.  Установите OCSWMIBC.MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > Пакет OCSWMIBC.msi должен быть установлен на компьютере, где выполняется мастер объединения построителя топологий. Однако рекомендуется устанавливать OCSWMIBC.msi на всех интерфейсных серверах в используемой топологии.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi можно установить на любой компьютер домена, на котором установлены основные компоненты Lync Server 2013 и Командная консоль Lync Server 2013, и получить доступ к топологии Office Communications Server 2007 R2 (AD DS to Active Directory Domain Services (AD DS) и SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

