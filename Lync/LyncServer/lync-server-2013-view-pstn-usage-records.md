---
title: 'Lync Server 2013: Просмотр записей об использовании PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9042eca0b8ddd1f04b34c3fea0b57dd6235b69c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Просмотр записей использования PSTN в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Запись использования общественной коммутируемой телефонной сети (PSTN) определяет класс вызова (например, внутренние, локальные или междугородние), которые могут быть сделаны различными пользователями или группами пользователей в Организации. Дополнительные сведения можно найти [в разделе записи использования PSTN в Lync Server 2013](lync-server-2013-pstn-usage-records.md) в документации по планированию.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Просмотр записи использования PSTN с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем — **Использование ТСОП**.

4.  На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.
    
    <div>
    

    > [!NOTE]  
    > На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений об использовании PSTN с помощью командлетов Windows PowerShell

Вы также можете просматривать использование PSTN с помощью Windows PowerShell и командлета **Get-кспстнусаже** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений об использовании PSTN с помощью командлетов Windows PowerShell

  - Чтобы просмотреть сведения о всех использовании PSTN, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД.
    
        Get-CsPstnUsage
    
    Этой командой возвращается информация, аналогичная следующим сведениям:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

Подробности можно найти в [статьях Get-кспстнусаже](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).

</div>

<div>

## <a name="see-also"></a>См. также


[Создание политики голосовой связи и настройка записей об использовании PSTN в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

