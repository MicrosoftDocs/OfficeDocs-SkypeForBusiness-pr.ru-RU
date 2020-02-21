---
title: 'Lync Server 2013: включение пользователей для единого хранилища контактов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4bd8e47259f7480f32e0fa6047657464a459de
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Включение пользователей для единого хранилища контактов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-07_

При развертывании Lync Server 2013 и публикации топологии единое хранилище контактов включено для всех пользователей по умолчанию. Для включения единого хранилища контактов после развертывания Lync Server 2013 не требуется предпринимать никаких дополнительных действий. Однако можно использовать командлет **Set-CsUserServicesPolicy**, чтобы указать, каким пользователям доступно единое хранилище контактов. Эту возможность можно включать глобально, по узлам, по клиентам, по отдельности или группами.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>Включение для пользователей единого хранилища контактов

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните любые из следующих действий.
    
      - Чтобы включить единое хранилище контактов глобально для всех пользователей Lync Server, в командной строке введите:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Чтобы включить единое хранилище контактов для пользователей на конкретном сайте, в командной строке введите следующую команду:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        For example:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Чтобы включить единое хранилище контактов по клиентам, в командной строке введите следующую команду:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Например:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Чтобы включить единое хранилище контактов для конкретных пользователей, в командной строке введите следующую команду:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > Вместо отображаемых имен пользователей можно использовать псевдонимы или SIP URI.

        
        </div>
        
        Например:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > В предыдущем примере первая команда создает новую политику на уровне пользователя с именем <EM>UCS Enabled Users</EM> и с флагом UcsAllowed, установленным в значение True. Вторая команда назначает эту политику пользователю с отображаемым именем Ken Myer, что означает, что теперь Кену Майеру разрешен доступ к единому хранилищу контактов.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

