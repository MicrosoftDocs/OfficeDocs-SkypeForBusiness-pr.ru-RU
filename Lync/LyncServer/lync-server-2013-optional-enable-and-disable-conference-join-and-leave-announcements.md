---
title: Необязательно Включение и отключение объявлений о присоединении и выходе из конференции
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
ms.openlocfilehash: 67939f67e90e6c0cc044ea871560647cae9e4021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>Необязательно Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-30_

Когда пользователи присоединяются к Конференции или покидают ее, приложение извещения о конференц-связи может сообщить о своем выходе или выходе, выполнив тон или произнести их имена. Вы можете изменить работу объявлений с помощью командлетов. Этот шаг является необязательным.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Изменение объявлений при присоединении к конференции и выходе из нее

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните в командной строке следующую команду:
    
        Get-CsDialinConferencingConfiguration
    
    Этот командлет получает сведения о том, требуются ли участникам для записи их имен при присоединении к Конференции, а также о том, как Lync Server отвечает, когда участники присоединяются к Конференции или покидают ее.

4.  Выполните в командной строке следующую команду:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **Енабленамерекординг**   определяет, запрашивается ли анонимным участникам запись своего имени перед входом в конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции. (Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)
    
    **Ентрекситаннаунцементсенабледбидефаулт**   указывает, включены ли объявления по умолчанию. Значение по умолчанию — "$false", что означает, что по умолчанию при присоединении или выходе участников из Конференции не будет извещений. Организатор собрания может переопределить этот параметр при планировании собрания.
    
    **Ентрекситаннаунцементстипе**   указывает действие, выполняемое каждый раз, когда участник присоединяется или покидает Конференцию, для которой включены извещения. Значение по умолчанию — "Усенамес", что означает, что существует сообщение, похожее на следующее: "Кен Myer присоединился к Конференции" при включении объявлений.
    
    Эти параметры можно настроить в глобальной области действия или на уровне сайта. Параметры, настроенные в области сайта, имеют приоритет над параметрами, настроенными в глобальной области.
    
    Например:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    В этом примере параметры настраиваются на уровне сайта для Redmond. Объявления включены, но при присоединении к Конференции участники не получают запрос на ввод имени. Звук воспроизводится, когда участники вводят или оставляют конференцию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

