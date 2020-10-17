---
title: 'Lync Server 2013: Просмотр сведений о абонентской схеме'
description: 'Lync Server 2013: Просмотр сведений о абонентской схеме.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4473302b182b8de4ea6aad12d7993cb5d442b7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569695"
---
# <a name="view-dial-plan-information-in-lync-server-2013"></a>Просмотр сведений о абонентской схеме в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Для просмотра сведений о существующей абонентской группе выполните действия, указанные в следующей процедуре. Если вы хотите создать новую абонентскую схему, ознакомьтесь со статьей [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a>Просмотр сведений о абонентской группы из панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите **Маршрутизация телефонных звонков** и нажмите **Абонентская группа**.

4.  На странице **Абонентская группа** дважды щелкните имя абонентской группы.
    
    <div>
    

    > [!NOTE]  
    > Можно одновременно просматривать не более одной абонентской группы.

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a>Просмотр абонентских планов с помощью командлетов Windows PowerShell

  - Абонентские группы можно просмотреть с помощью интерфейса командной строки Windows PowerShell и командлета **Get – CsDialPlan** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Чтобы просмотреть сведения обо всех абонентских планах, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:
    
        Get-CsDialPlan
    
    Эта команда возвращает приблизительно следующие сведения:
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a>См. также


[Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

