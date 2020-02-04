---
title: 'Lync Server 2013: Создание политики размещенной голосовой почты на уровне сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Создание политики размещенной голосовой почты на уровне сайта в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Политика *сайта* может влиять на всех пользователей, которые размещены на сайте, для которого определена политика. Если пользователь настроен на доступ к размещенной единой системе обмена сообщениями в UM и для него не назначена политика на уровне пользователя, применяется политика сайта. Если вы не развернули политику сайта, она будет применена к глобальной политике.

Дополнительные сведения о настройке политик сайтов можно найти в документации по оболочке управления Lync Server для следующих командлетов:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Создание политики размещенной голосовой почты сайта

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите командлет New-Кшостедвоицемаилполици, чтобы создать политику. Например, выполните командлет:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    В этом примере создается политика размещенной голосовой почты с областью сайта и устанавливаются следующие параметры:
    
      - **Identity** — уникальный идентификатор для политики, включающий область. Для политики с областью сайта значение параметра удостоверения должно быть задано в `site:` * \<имени\>* формата, например. `site:Redmond`
    
      - **Destination** указывает полное доменное имя (FQDN) размещенной службы единой системы обмена сообщениями. Этот параметр является необязательным, но при попытке включить пользователя для размещенной голосовой почты и назначенной пользователю политики не может быть задано значение "включить".
    
      - **Описание** — необязательные описательные сведения о политике.
    
      - **Организация** : список клиентов Exchange, разделенных запятыми, которые пользователи Lync Server 2013. Каждый клиент должен быть указан в качестве полного доменного имени этого клиента в размещенной службе единой системы обмена сообщениями.

</div>

</div>

<span> </span>

</div>

</div>

</div>

