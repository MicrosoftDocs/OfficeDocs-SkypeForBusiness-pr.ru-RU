---
title: 'Lync Server 2013: предоставление разрешений на установку'
description: 'Lync Server 2013: предоставление разрешений на установку.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554485"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a>Предоставление разрешений на установку в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-27_

Командлет **Grant-CsSetupPermission** можно использовать для добавления разрешений уровня Read, Write, ReadSPN и WriteSPN в группу RTCUniversalServerAdmins для указанного подразделения Active Directory. Затем члены группы RTCUniversalServerAdmins в этом подразделении могут устанавливать серверы, на которых работает Lync Server 2013, в указанном домене, не выполняя членство в группе "Администраторы домена".

Используйте командлет **Test-CsSetupPermission** для проверки разрешений, заданных с помощью командлета **Grant-CsSetupPermission**.

Командлет **Revoke-CsSetupPermission** можно использовать для удаления разрешений, предоставленных с помощью командлета **Grant-CsSetupPermission**.

<div>

## <a name="to-grant-setup-permissions"></a>Порядок предоставления разрешений на установку

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите предоставить разрешения на установку. Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.
    
    Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Проверка разрешений на установку

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором необходимо проверить разрешения программы установки, предоставленные с помощью командлета **Grant – CsSetupPermission** . Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.
    
    Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Аннулирование разрешений на установку

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домене, для которого требуется отозвать разрешения на установку, предоставленные командлетом **Grant – CsSetupPermission** . Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Можно указать параметр ComputerOu в соответствии с контекстом именования по умолчанию указанного домена (например, CN=Computers). Кроме того, можно указать этот параметр как полное различающееся имя подразделения (например, CN=Computers, DC=Contoso, dc=com). В последнем случае необходимо указать полное различающееся имя подразделения, соответствующее указанному домену.
    
    Если параметр «Домен» не указан, по умолчанию в качестве значения используется локальный домен.

</div>

</div>

<span> </span>

</div>

</div>

</div>

