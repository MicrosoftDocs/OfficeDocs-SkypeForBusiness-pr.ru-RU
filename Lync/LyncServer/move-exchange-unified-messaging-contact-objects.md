---
title: Перемещение объектов контактов единой системы обмена сообщениями Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Перемещение объектов контактов единой системы обмена сообщениями Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

Для миграции объектов контактов для автосекретаря (AA) и доступа к подписчикам (SA) на новый сервер Lync Server 2013 сначала нужно переместить объекты из устаревшего развертывания Office Communications Server 2007 R2 в новое развертывание Lync Server 2013 с помощью ** Командлеты Get-Ксексумконтакт** и **Move-ксексумконтакт** . На сервере Exchange Server вы можете запустить сценарий Windows PowerShell **ексчукутил** , чтобы сделать следующее для вновь развернутого пула Lync:

  - Добавьте его в IP-шлюз единой системы обмена сообщениями.

  - Добавьте его в группу слежения единой системы обмена сообщениями.

<div>


> [!NOTE]  
> Чтобы использовать командлеты <STRONG>Get-ксексумконтакт</STRONG> и <STRONG>Move-ксексумконтакт</STRONG> , вы должны быть участником группы РТКУНИВЕРСАЛУСЕРАДМИНС и иметь разрешение OU на подразделение, в котором хранятся объекты контактов. Разрешение OU можно предоставить с помощью командлета <STRONG>Grant-аупермиссион</STRONG> .



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Перемещение объектов контакта с помощью командной консоли Lync Server Management Shell

1.  Откройте командную консоль Lync Server Management Shell.

2.  Для каждого пула, зарегистрированного в единой системе обмена сообщениями Exchange (где pool1.contoso.net — это пул из конфигурации Office Communications Server 2007 R2 и pool2.contoso.net — это пул из развертывания Lync Server 2013), введите следующую команду:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Чтобы убедиться в том, что объекты контакта перемещены, выполните командлет **Get-ксексумконтакт** и убедитесь, что в **регистрарпул** указывает на новый пул.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Выполнение сценария Windows PowerShell Ексчукутил

1.  Войдите на сервер Exchange UM как пользователь с правами администратора организации Exchange.

2.  Перейдите на Ексчукутил сценарий Windows PowerShell.
    
    В Exchange 2007 Ексчукутил. ps1 размещается по адресу: **% Program\\Files\\%\\Scripts\\сервера Microsoft Exchange Server ексчукутил. ps1**
    
    В Exchange 2010 Ексчукутил. ps1 расположен по адресу: **% Program Files\\%\\Microsoft Exchange\\Server\\V14\\Scripts ексчукутил. ps1**

3.  Если Exchange развернут в одном лесе, введите:
    
        exchucutil.ps1
    
    Если Exchange развернут в нескольких лесах, введите:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    где полное доменное имя леса определяет лес, в котором развернут Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > <EM>После</EM> запуска ексчукутил. ps1 убедитесь в том, что вы перезапустите службу <STRONG>внешнего сервера Lync Server</STRONG> (ртксрв. exe). В противном случае Lync Server 2013 не будет определять единую систему обмена сообщениями в топологии.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

