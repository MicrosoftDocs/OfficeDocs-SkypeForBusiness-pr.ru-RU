---
title: 'Lync Server 2013: изменение политики глобальной размещенной голосовой почты'
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
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Изменение политики глобальной размещенной голосовой почты в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Политика *глобальной* размещенной голосовой почты устанавливается вместе с Lync Server 2013. Вы можете изменить его в соответствии с вашими потребностями, но переименовать или удалить его будет невозможно. Чтобы изменить глобальную политику, используйте командлет Set-Кшостедвоицемаилполици, чтобы установить для параметров соответствующие значения для конкретного развертывания.

Дополнительные сведения о командлете [Set-кшостедвоицемаилполици](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) можно найти в документации по оболочке Lync Server Management Shell.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Изменение политики глобальной размещенной голосовой почты

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите командлет Set-Кшостедвоицемаилполици, чтобы настроить параметры глобальной политики для вашей среды. Например, выполните командлет:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Так как эта команда не задает параметр удостоверения политики, интерфейс командной строки Windows PowerShell задает указанные ниже значения для политики глобальной размещенной голосовой почты.
    
      - **Destination** указывает полное доменное имя (FQDN) размещенной службы единой системы обмена сообщениями. Этот параметр является необязательным, но при попытке включить пользователя для размещенной голосовой почты и назначенной пользователю политики не может быть задано значение "включить".
    
      - В разделе **Организация** указывается список клиентов Exchange, разделенных запятыми, которые пользователи Lync Server имеют дома. Каждый клиент должен быть указан в качестве полного доменного имени этого клиента в размещенной службе единой системы обмена сообщениями.
    
    <div>
    

    > [!NOTE]  
    > В предыдущем примере значение "corp1.litwareinc.com" заменяет любое значение, которое может быть уже представлено в параметре "Организация". Например, если в политике уже указан список организаций с разделителями-запятыми, весь список будет заменен. Если вы хотите добавить в список организацию вместо замены всего списка, выполните команду, подобную следующей:

    
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

