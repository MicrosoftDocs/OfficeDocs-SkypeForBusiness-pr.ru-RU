---
title: Включение и отключение объявлений о присоединении и выходе из конференции (необязательно)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013 (необязательно)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-30_

При присоединении к Конференции или выходе из нее пользователи могут сообщать о своем входе в приложение и выходить из него с помощью звукового сопровождения или произнесения их имен. Вы можете изменить способ работы объявлений, выполнив командлеты. Этот шаг является необязательным.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Изменение объявлений при присоединении к конференции и выходе из нее

1.  Войдите в систему под учетной записью члена группы Рткуниверсалсерверадминс или члена роли **CS-серверадминистратор** или **ксадминистратор** .

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду в командной строке:
    
        Get-CsDialinConferencingConfiguration
    
    Этот командлет извлекает сведения о том, требуется ли участникам записывать свое имя при присоединении к Конференции, а также о том, как Lync Server отвечает за присоединение или выход из конференции с телефонным подключением.

4.  Выполните следующую команду в командной строке:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **Енабленамерекординг**   определяет, должны ли анонимные участники запрашивать запись имени перед входом в конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам будет предложено указать свое имя при присоединении к Конференции. (Участники, прошедшие проверку подлинности, не записывают свое имя, так как вместо этого используется отображаемое имя.)
    
    **Ентрекситаннаунцементсенабледбидефаулт**   указывает, включены ли извещения по умолчанию. Значением по умолчанию является "$false, что означает, что по умолчанию при присоединении к Конференции или выходе участников из нее не будет извещений. Организатор собрания может переопределить этот параметр при планировании собрания.
    
    **Ентрекситаннаунцементстипе**   указывает действие, предпринимаемое каждый раз, когда участник присоединяется к Конференции, для которой включены извещения, или выходит из нее. По умолчанию используется значение "Усенамес", которое означает, что на Конференции было объявлено извещение о том, что "Кен мер входит в конференцию", когда извещения включены.
    
    Эти параметры можно настроить в глобальной области или в области узла. Параметры, настроенные в области узла, имеют более высокий приоритет, чем параметры, настроенные в глобальной области.
    
    Например:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    В этом примере параметры задаются в области сайта для Redmond. Объявления включены, но у участников не запрашивается имя при подключении к конференции. Звуковой сигнал воспроизводится, когда участники вводят или покидают Конференцию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

