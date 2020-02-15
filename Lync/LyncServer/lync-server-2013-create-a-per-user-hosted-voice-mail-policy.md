---
title: 'Lync Server 2013: Создание политики размещенной голосовой почты для отдельных пользователей'
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
ms.openlocfilehash: 055d65fe691d99c8b960ebed088ba47cbcb2f988
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Создание политики размещенной голосовой почты на уровне пользователя в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-24_

Новая политика *на уровне пользователя* может оказывать влияние только на отдельных пользователей, группы и контактные объекты. Для развертывания политики на уровне пользователя необходимо явно назначить политику отдельным пользователям, группам или контактным объектам. Дополнительные сведения приведены [в статье назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Дополнительные сведения о работе с размещенными политиками голосовой почты для отдельных пользователей представлены в документации по командной консоли Lync Server для следующих командлетов:

  - [New — CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set — CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>Создание политики маршрутизации размещенной голосовой почты на уровне пользователя

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Запустите командлет New-CsHostedVoicemailPolicy для создания политики. Например, выполните следующую команду:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    В этом примере создается политика размещенной голосовой почты на уровне пользователя и задаются следующие параметры.
    
      - **Удостоверение** — задает уникальный идентификатор для политики, охватывающей указанную область. Для политики на уровне пользователя это значение задается в виде простой строки, например ExRedmond.
    
      - **Назначение** — задает полное доменное имя размещенной службы единой системы обмена сообщениями Exchange. Этот параметр является необязательным, но если для политики, назначенной пользователю, этот параметр не задан, и вы пытаетесь активировать размещенную голосовую почту для пользователя, произойдет сбой активации.
    
      - **Описание** — предоставляет дополнительное описание этой политики.
    
      - **Организация** — указывает разделенный запятыми список клиентов Exchange, которым пользователи Lync Server 2013 имеют доступ к домашнему серверу. Каждый клиент должен быть указан в виде полного доменного имени клиента в размещенной службе единой системы обмена сообщениями Exchange.

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение политики размещенной голосовой почты на уровне пользователя в Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

