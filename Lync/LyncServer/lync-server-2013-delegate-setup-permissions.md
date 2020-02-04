---
title: 'Lync Server 2013: делегирование разрешений на установку'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Делегирование разрешений на установку в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-05_

Если вы не хотите предоставлять членство в группе "Администраторы домена" пользователям или группам, которые развертывают Lync Server 2013, вы можете включить членов группы рткуниверсалсерверадминс для запуска командлета Windows PowerShell **Enable-кстопологи** на серверах с Lync Server 2013. По умолчанию участники группы Рткуниверсалсерверадминс не могут выполнять этот командлет. Вы можете предоставить права администратора и разрешения на запуск команды **Enable-кстопологи** на серверах с Lync Server, используя командлет **Grant-кссетуппермиссион** и УКАЗАВ подразделение (OU), в котором находятся объекты компьютеров для сервера с Lync Server 2013.

Подготовка домена, которая выполняется при установке Lync Server, не добавляет автоматически разрешения, позволяющие членам группы Рткуниверсалсерверадминс запускать командлет Enable-Кстопологи. Это означает, что по умолчанию вы должны быть администратором домена, чтобы включить топологию. Чтобы предоставить участникам группы Рткуниверсалсерверадминс право на включение топологии, необходимо запустить командлет Grant-Кссетуппермиссионс. Кроме того, вам потребуется выполнить этот командлет для каждого контейнера Active Directory, который используется для работы компьютеров с Lync Server.

Имейте в виду, что этот командлет предоставляет разрешения только группе Рткуниверсалсерверадминс; Этот командлет не может использоваться для предоставления разрешений другим группам безопасности или отдельным пользователям.

<div>


> [!NOTE]  
> <STRONG>Enable-кстопологи</STRONG> — это ключевой командлет, позволяющий членам группы рткуниверсалсерверадминс настраивать и развертывать Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Добавление возможности запуска команды Enable-Кстопологи в группу Рткуниверсалсерверадминс

1.  Войдите на сервер в качестве участника группы "Администраторы домена" для домена, на котором делегированный пользователь будет выполнять **функцию Enable-кстопологи**.

2.  Откройте консоль управления Lync Server 2013. Управляющая консоль Lync Server 2013 автоматически устанавливается на каждый сервер переднего плана или на любой компьютер, на котором установлены средства администрирования Lync Server 2013. Подробные сведения о командной консоли Lync Server 2013 можно найти в руководстве по [управлению Lync server 2013](lync-server-2013-lync-server-management-shell.md) в документации по эксплуатации.

3.  Запустите из командной консоли Lync Server 2013 следующий командлет:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Если подразделение имеет верхний уровень, необходимо указать полное доменное имя.

    
    </div>
    
    В приведенном ниже примере подразделением является "серверы Lync", которые находятся в домене contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

