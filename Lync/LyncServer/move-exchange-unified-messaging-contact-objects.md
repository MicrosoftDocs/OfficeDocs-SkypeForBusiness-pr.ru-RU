---
title: Перемещение контактных объектов единой системы обмена сообщениями Exchange
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b3091a342b46b5c1aad1d456aa9159d951a4ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Перемещение контактных объектов единой системы обмена сообщениями Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Для переноса контактных объектов автосекретаря (AA) и абонентского доступа (SA) в новое развертывание Lync Server 2013 сначала необходимо переместить объекты из устаревшего развертывания Office Communications Server 2007 R2 в новое развертывание Lync Server 2013 с помощью командлетов **Get-CsExUmContact** и **Move-CsExUmContact** . Затем на сервере Exchange выполните сценарий Windows PowerShell **сценарий ExchUCUtil** , чтобы выполнить следующие действия для вновь развернутого пула Lync:

  - Добавить его в шлюз IP единой системы обмена сообщениями.

  - Добавить его в сервисные группы единой системы обмена сообщениями.

<div>


> [!NOTE]  
> In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Перемещение контактных объектов с помощью командной консоли Lync Server

1.  Откройте командную консоль Lync Server.

2.  Для каждого пула, зарегистрированного в единой системе обмена сообщениями Exchange (где pool1.contoso.net — это пул из развертывания Office Communications Server 2007 R2 и pool2.contoso.net — это пул из развертывания Lync Server 2013), в командной строке введите следующую команду:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Чтобы проверить успешность перемещения контактных объектов, выполните командлет **Get-CsExumContact** и убедитесь, что **RegistrarPool** теперь указывает на новый пул.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Выполнение скрипта ExchUCUtil Windows PowerShell

1.  Войдите на сервер Exchange Server с единой системой обмена сообщениями как пользователь с привилегиями администратора организации в Exchange.

2.  Перейдите к скрипту Windows PowerShell сценарий ExchUCUtil.
    
    В Exchange 2007 ExchUCUtil.ps1 находится по адресу: **% Program Files% \\ Microsoft \\ Exchange Server \\ scripting \\ExchUCUtil.ps1**
    
    В Exchange 2010 ExchUCUtil.ps1 расположен по адресу: **% Program Files% \\ Microsoft \\ Exchange Server \\ V14 \\ Scripts \\ExchUCUtil.ps1**

3.  Если Exchange развертывается в одном лесу, введите:
    
        exchucutil.ps1
    
    Если Exchange развертывается в нескольких лесах, введите:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    где полное доменное имя леса указывает лес, в котором развернут Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Обязательно перезапустите службу <STRONG>Сервер переднего плана Lync Server</STRONG> (rtcsrv.exe) <EM>после</EM> выполнения скрипта exchucutil.ps1. В противном случае Lync Server 2013 не будет обнаруживать единую систему обмена сообщениями в топологии.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

