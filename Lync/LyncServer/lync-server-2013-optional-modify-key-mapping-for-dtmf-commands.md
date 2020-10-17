---
title: 'Lync Server 2013: изменение сопоставления клавиш для команд DTMF (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7104a24c7bf02c310cb1deb7b8f9de3ad51407c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524426"
---
# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>Необязательно Изменение сопоставления клавиш для команд DTMF в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-30_

Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона. Изменить назначения клавиш, используемых для команд DTMF, можно с помощью командлетов. Это действие необязательно.

<div>


> [!NOTE]  
> Для получения дополнительных сведений об этих командлетах и возможных параметрах DTMF ознакомьтесь с документацией по среде управления Lync Server или командной консоли Lync Server Management Shell.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Изменение сопоставления команд DTMF

1.  Войдите на компьютер как член группы **RTCUniversalServerAdmins** или роли **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующую команду в командной строке:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Этот командлет возвращает параметры DTMF, используемые для конференц-связи с телефонным подключением.

4.  Выполните следующий командлет и укажите клавишу, назначаемую каждому параметру, который требуется изменить:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Этот командлет изменяет параметры DTMF, используемые для конференц-связи с телефонным подключением.
    
    Пример:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    В этом примере функции клавиш включения и отключения объявлений, а также включения и отключения звука всех участников меняются местами. Поскольку не указано значение параметра Identity, эти изменения применяются к глобальным параметрам DTMF.

5.  Необязательно Чтобы создать дополнительные наборы команд DTMF для определенных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration** с идентификатором сайта. При создании новых параметров DTMF для сайтов параметры сайта имеют приоритет над глобальными параметрами. Дополнительные сведения см. в документации по среде управления Lync Server или командной консоли командной консоли Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

