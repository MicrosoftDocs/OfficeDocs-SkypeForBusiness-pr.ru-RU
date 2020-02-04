---
title: 'Lync Server 2013: включение поддержки размещаемой голосовой почты для пользователей'
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
ms.openlocfilehash: 8e0ce9ee4da6ee0a36e5e5f0028371aab8af523f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Включение поддержки размещаемой голосовой почты для пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Следуйте инструкциям, чтобы включить пользователей Lync Server 2013 для голосовой почты в размещенной службе единой системы обмена сообщениями Exchange.

Дополнительные сведения можно найти [в разделе Управление пользователями Exchange в среде Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) в документации по планированию.

Дополнительные сведения о командлете [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) можно найти в документации по оболочке Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Прежде чем пользователи Lync Server 2013 могут быть включены для поддержки размещенной голосовой почты, необходимо развернуть политику размещенной голосовой почты, которая применяется к учетной записи пользователя. Подробнее смотрите в разделе <A href="lync-server-2013-hosted-voice-mail-policies.md">политики размещенной голосовой почты в Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Предоставление пользователям размещенной голосовой почты

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите командлет Set-CsUser, чтобы настроить учетную запись пользователя для размещенной голосовой почты. Например, выполните следующую команду:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    Команда в предыдущем примере задает следующие параметры:
    
      - **Хостедвоицемаил** позволяет перенаправлять голосовую почту пользователя на размещенную в единой системе обмена сообщениями. Она также сообщает Microsoft Lync 2013 о том, что у вас есть индикатор "позвонить голосовой почте".
    
      - **Identity** указывает учетную запись пользователя, который нужно изменить. Значение идентификатора можно задать в одном из следующих форматов:
        
          - Адрес SIP пользователя
        
          - Имя субъекта-пользователя в службе каталогов Active Directory
        
          - Доменное\\имя пользователя (например, Contoso\\кенмер).
        
          - Отображаемое имя доменных служб Active Directory (например, Кен мер). Если в качестве значения удостоверения используется имя для отображения, можно использовать подстановочный знак "звездочка" (\*). Например, удостоверение "\* Иванов" возвращает всех пользователей, у которых есть имя отображения, которое оканчивается строковым значением Смит.
        
        <div>
        

        > [!NOTE]  
        > Имя учетной записи SAM в Active Directory не может использоваться в качестве значения удостоверения, так как имя SAM-Account-Name не обязательно должно быть уникальным в лесу.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

