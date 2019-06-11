---
title: 'Lync Server 2013: проверка назначения регионов абонентским группам'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5aa91470accf0f25478b9233e1efb90357251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Проверка абонентских планов Lync Server 2013 назначенные регионы

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2010-11-02_

Для абонентской группы, используемой для конференц-связи с телефонным подключением, необходимо указать **регион Конференц** -связи с телефонным подключением, чтобы связать номера доступа для конференц-связи с телефонным подключением с помощью соответствующей абонентской группы. При создании абонентской группы следует задать регион конференц-связи с телефонным подключением, применяемый к этой абонентской группе. Затем, когда вы создадите номер доступа для телефонного подключения, вы выбираете регионы, связывающие номер доступа с соответствующими абонентской абонентской панелью.

Так как важно указать регион для всех абонентов, мы рекомендуем использовать эту процедуру, чтобы убедиться, что все абонентские группы имеют регионы. Этот шаг является необязательным.

С помощью командлета **Get-ксдиалплан** убедитесь, что регион задан для всех абонентских планов для конференц-связи с телефонным подключением. If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region. Вы также можете использовать панель управления Lync Server для обновления региона в существующих абонентских тарифах. Подробнее об использовании панели управления Lync Server можно найти [в разделе Изменение абонентской группы в Lync server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Проверка правильности задания регионов для абонентских групп

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду в командной строке:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Например:
    
        Get-CsDialPlan
    
    В данном примере возвращаются все абонентские группы, настроенные для вашей организации.

4.  Просмотрите возвращенные абонентские группы, чтобы выявить те из них, для которых не задан регион конференц-связи с телефонным подключением. Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Установка свойства региона для абонентской группы

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Для всех абонентских групп, у которых не задан регион конференц-связи с телефонным подключением, выполните следующую команду:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Например:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    В данном примере изменяется абонентская группа с идентификатором Redmond –  для ее свойства DialinConferencingRegion устанавливается значение «US West Coast». Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

