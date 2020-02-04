---
title: 'Lync Server 2013: Создание политики для размещенной голосовой почты для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Создание политики размещенной голосовой почты для каждого пользователя в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Политика *для пользователей* может влиять только на отдельных пользователей, группы и объекты контактов. Чтобы развернуть политику для пользователя, необходимо явно назначить ее одному или нескольким пользователям, группам или контактным объектам. Подробности можно найти [в разделе Назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Дополнительные сведения о работе с политиками голосовой почты для отдельных пользователей можно найти в документации по оболочки управления Lync Server для следующих командлетов:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>Создание политики размещенной голосовой почты для пользователя

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите командлет New-Кшостедвоицемаилполици, чтобы создать политику. Например, выполните командлет:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    В предыдущем примере создается политика размещенной голосовой почты с областью "на пользователя" и устанавливаются следующие параметры:
    
      - **Identity** — уникальный идентификатор для политики, включающий область. Для политики с областью "на пользователя" Этот параметр указывает на простое строковое значение, например Ексредмонд.
    
      - **Destination** указывает полное доменное имя (FQDN) размещенной службы единой системы обмена сообщениями. Этот параметр является необязательным, но при попытке включить пользователя для размещенной голосовой почты и назначенной пользователю политики не может быть задано значение "включить".
    
      - **Описание** — необязательные описательные сведения о политике.
    
      - **Организация** : список клиентов Exchange, разделенных запятыми, которые пользователи Lync Server 2013. Каждый клиент должен быть указан в качестве полного доменного имени этого клиента в размещенной службе единой системы обмена сообщениями.

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

