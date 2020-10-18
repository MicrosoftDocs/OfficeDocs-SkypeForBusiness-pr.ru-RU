---
title: 'Lync Server 2013: Включение поддержки размещенной голосовой почты для пользователей'
description: 'Lync Server 2013: Включение поддержки размещенной голосовой почты для пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3853a70d433c09029a02f2ca6256b5988defdcb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572745"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Предоставление пользователям размещенной голосовой почты в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-24_

Следуйте инструкциям по включению поддержки пользователями Lync Server 2013 для голосовой почты в размещенной службе единой системы обмена сообщениями Exchange.

Для получения дополнительных сведений см в документации по планированию [Hosted Management управление пользователями в Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) .

Подробные сведения о командлете [Set – CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) можно найти в документации по консоли управления Lync Server.

<div>


> [!IMPORTANT]  
> Прежде чем можно будет включить поддержку размещенной голосовой почты для пользователя Lync Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к учетной записи пользователя. Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>To enable users for hosted voice mail

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет Set-CsUser, чтобы настроить учетную запись пользователя для размещаемой голосовой почты. Например, выполните команду:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    Команда в предыдущем примере задает следующие параметры:
    
      - **HostedVoiceMail** включает маршрутизацию вызовов голосовой почты пользователей в размещаемую единую систему обмена сообщениями Exchange. Он также сообщает Microsoft Lync 2013, чтобы получить индикатор "позвонить голосовой почте".
    
      - **Identity** ? указывает изменяемую учетную запись. Значение Identity можно указать, используя следующие форматы:
        
          - SIP-адрес пользователя;
        
          - имя участника-пользователя Active Directory пользователя;
        
          - Имя для входа в домен пользователя \\ (например, Contoso \\ kenmyer).
        
          - отображаемое имя доменных служб Active Directory пользователя (например, Ken Myer). При использовании Display-Name в качестве значения идентификатора можно использовать подстановочный знак "звездочка" ( \* ). Например, идентификатор " \* Smith" возвращает всех пользователей, у которых есть Display-Name, заканчивающийся строковым значением "Smith".
        
        <div>
        

        > [!NOTE]  
        > Имя-учетной-записи-SAM Active Directory пользователя нельзя использовать в качестве значения параметра Identity, так как это имя может быть неуникальным в лесу.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

