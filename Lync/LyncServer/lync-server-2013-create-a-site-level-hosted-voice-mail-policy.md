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
ms.openlocfilehash: e23f14b1db7c846d5dbaa0aa6861274a7b6a2611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501886"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Создание политики размещенной голосовой почты на уровне сайта в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-24_

Политика *сайта* может повлиять на всех пользователей, размещенных на сайте, для которого определена политика. Если пользователь настраивается для доступа к размещенной единой системе обмена сообщениями Exchange и не имеет политики на уровне пользователя, применяется политика сайта. Если политика сайта не развернута, применяется Глобальная политика.

Для получения дополнительных сведений о настройке политик сайтов обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [New — CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set — CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Создание политики размещенной голосовой почты сайта

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Запустите командлет New-CsHostedVoicemailPolicy для создания политики. Например, выполните следующую команду:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    В этом примере создается политика размещенной голосовой почты с областью сайта, а также задаются следующие параметры:
    
      - **Удостоверение** — задает уникальный идентификатор для политики, охватывающей указанную область. Для политики с областью сайта значение параметра Identity должно быть указано в формате `site:` *\<name\>* , например `site:Redmond` .
    
      - **Назначение** — задает полное доменное имя размещенной службы единой системы обмена сообщениями Exchange. Этот параметр является необязательным, но если для политики, назначенной пользователю, этот параметр не задан, и вы пытаетесь активировать размещенную голосовую почту для пользователя, произойдет сбой активации.
    
      - **Описание** — предоставляет дополнительное описание этой политики.
    
      - **Организация** — указывает разделенный запятыми список клиентов Exchange, которым пользователи Lync Server 2013 имеют доступ к домашнему серверу. Каждый клиент должен быть указан в виде полного доменного имени клиента в размещенной службе единой системы обмена сообщениями Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

