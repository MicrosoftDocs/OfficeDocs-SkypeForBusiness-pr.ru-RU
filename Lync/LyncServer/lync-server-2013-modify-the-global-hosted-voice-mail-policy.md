---
title: 'Lync Server 2013: изменение глобальной политики размещенной голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9a7e9dcb3c626c076d51fa32fa195f0787a922c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515176"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Изменение глобальной политики размещенной голосовой почты в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-24_

*Глобальная* политика размещенной голосовой почты устанавливается вместе с Lync Server 2013. Вы можете изменить ее в соответствии со своими требованиями, но переименование или удаление этой политики невозможно. Чтобы изменить глобальную политику, можно использовать командлет Set-CsHostedVoicemailPolicy для присвоения параметрам соответствующих значений для конкретного развертывания.

Подробные сведения о командлете [Set – CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) можно найти в документации по консоли управления Lync Server.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Изменение глобальной размещенной политики голосовой почты

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет Set-CsHostedVoicemailPolicy, чтобы задать параметры глобальной политики для среды. Например, выполните:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Так как эта команда не задает параметр Identity политики, интерфейс командной строки Windows PowerShell задает следующие значения в глобальной размещенной политике голосовой почты:
    
      - **Назначение** — задает полное доменное имя размещенной службы единой системы обмена сообщениями Exchange. Этот параметр является необязательным, но если для политики, назначенной пользователю, этот параметр не задан, и вы пытаетесь активировать размещенную голосовую почту для пользователя, произойдет сбой активации.
    
      - **Организация** — указывает разделенный запятыми список клиентов Exchange, которые пользователи домашней среды Lync Server. Каждый клиент должен быть указан в виде полного доменного имени клиента в размещенной службе Exchange UM.
    
    <div>
    

    > [!NOTE]  
    > В командлете, представленном в предыдущем примере, значение «corp1.litwareinc.com» заменяет любое значение, которое может быть уже представлено в параметре «Организация». Например, если политика уже содержит список организаций с разделителями-запятыми, полный список будет заменен. Если необходимо добавить организацию в список, а не заменять его целиком, выполните команду, аналогичную следующей.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

