---
title: 'Lync Server 2013: Убедитесь, что абонентским группам назначены регионы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f25ca766ab7292aeeba0d2e621eccff5a0c47fb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Убедитесь, что в телефонных планах Lync Server 2013 назначены регионы

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2010-11-02_

Для абонентских групп, используемых при конференц-связи с телефонным подключением, должен быть указан **Dial-in conferencing region** (Регион конференц-связи с телефонным подключением), чтобы связать номера доступа к конференц-связи с телефонным подключением с соответствующей абонентской группой. При настройке абонентской группы вы указываете применяемый к ней регион конференц-связи с телефонным подключением. Потом при создании номеров доступа для телефонного подключения вы выбираете регионы, которые связывают номер доступа с соответствующими абонентскими группами.

Поскольку важно указать регион для всех абонентских групп, мы рекомендуем вам использовать данную процедуру, чтобы проверить наличие регионов у всех абонентских групп. Этот этап не является обязательным.

Используйте командлет **Get-CsDialPlan**, чтобы убедиться, что регион установлен для всех абонентских групп конференц-связи с телефонным подключением. Если регион для абонентских групп не задан, вы можете воспользоваться командлетом **Set-CsDialPlan** и задать такой регион. Вы также можете использовать панель управления Lync Server для обновления региона в существующих абонентских планах. Более подробную информацию об использовании панели управления Lync Server можно узнать [в статье Изменение абонентской группы в Lync server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Проверка правильности задания регионов для абонентских групп

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующую команду в командной строке:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Например:
    
        Get-CsDialPlan
    
    В данном примере возвращаются все абонентские группы, настроенные для вашей организации.

4.  Просмотрите возвращенные абонентские группы, чтобы выявить те из них, для которых не задан регион конференц-связи с телефонным подключением. Дополнительные сведения см. в документации Lync Server Management Shell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Установка свойства региона для абонентской группы

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Для всех абонентских групп, у которых не задан регион конференц-связи с телефонным подключением, выполните следующую команду:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Например:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    В данном примере изменяется абонентская группа с идентификатором Redmond — для ее свойства DialinConferencingRegion устанавливается значение «US West Coast». Дополнительные сведения см. в документации Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

