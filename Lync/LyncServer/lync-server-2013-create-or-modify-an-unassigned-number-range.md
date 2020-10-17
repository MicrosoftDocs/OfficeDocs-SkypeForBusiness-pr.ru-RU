---
title: 'Lync Server 2013: создание или изменение диапазона неназначенных номеров'
description: 'Lync Server 2013: создание или изменение диапазона неназначенных номеров.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2998616b931e94c9c38fc44d569b84b3af37709d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546955"
---
# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Создание или изменение диапазона неназначенных номеров в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Используйте одну из следующих процедур для настройки диапазонов неназначенных номеров для приложения оповещений.

<div>


> [!IMPORTANT]  
> Перед настройкой таблицы неназначенных номеров требуется определить оповещения или настроить автосекретарь единой системы обмена сообщениями Exchange.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Настройка неназначенных телефонных номеров с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Функции голосовых служб**, а затем выберите **Неназначенный номер**.

4.  На странице **Неназначенный номер** выполните одно из следующих действий:
    
      - Чтобы создать новый диапазон номеров, выберите **Создать**. В поле **Имя** введите имя для этого диапазона номеров.
        
        <div>
        

        > [!NOTE]  
        > После записи нового диапазона неназначенных номеров в базе данных вы не сможете изменить имя диапазона.

        
        </div>
    
      - Чтобы изменить существующий диапазон номеров, введите его имя целиком (или же его часть) в поле поиска. В списке найденных диапазонов номеров щелкните нужное имя, выберите **Изменить**, аз щелкните **Подробнее**.

5.  В первом поле **Диапазон номеров** введите первый номер диапазона, а во втором поле **Диапазон номеров** введите последний номер диапазона.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</P>
    > <LI>
    > <P>Если начальный или конечный номер диапазона содержит добавочный номер, то и начальный, и конечный номера диапазона должны содержать добавочный номер, который должен быть одинаковым для обоих номеров.</P>
    > <LI>
    > <P>Число должно быть согласовано с регулярным выражением (Tel:)? ( \+ )? [1-9] \d {0,17} (; ext = [1-9] \d {0,9} )?. Это означает, что номер должен начинаться со строки "tel:" (если эта строка не указана, она будет добавлена автоматически), знака "плюс" (+) и цифры от 1 до 9. Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</P></LI></UL>

    
    </div>

6.  В диалоговом окне **Служба объявлений** выполните одно из следующих действий:
    
      - Щелкните **Объявление**.
    
      - Щелкните **Единая система обмена сообщениями Exchange**.

7.  Если при выполнении предыдущего шага вы щелкнули **Объявление**, выполните следующие действия.
    
    1.  В разделе **Полное доменное имя конечного сервера**, нажмите кнопку **Выбрать**, щелкните идентификатор службы приложения, выполняющую приложение объявлений, которое будет обрабатывать входящие вызовы для этого диапазона неназначенных номеров, а затем нажмите кнопку **ОК**.
    
    2.  В окне **Объявление** щелкните объявление, которое будет воспроизводиться для этого диапазона неназначенных номеров.

8.  Если при выполнении предыдущего шага вы щелкнули**Единая система обмена сообщениями Exchange**, в разделе ** Номер телефона автосекретаря** нажмите кнопку **Выбрать**, щелкните номер телефона, который будет использоваться для данного диапазона неназначенных чисел, а затем нажмите кнопку **ОК**.

9.  Нажмите кнопку **ОК**.

10. Убедитесь, что на странице **Неназначенный номер** диапазоны неназначенных номеров расположены в требуемом порядке. Чтобы изменить расположение диапазона в таблице, выберите одно или несколько смежных имен в списке диапазонов, а затем щелкните стрелки вверх или вниз.
    
    <div>
    

    > [!TIP]  
    > Lync Server выполняет поиск в таблице неназначенных номеров сверху вниз и использует первый диапазон, соответствующий неназначенному номеру. При наличии перекрывающихся диапазонов и одного диапазона, который задает последнее возможное действие, убедитесь, что этот диапазон находится внизу списка.

    
    </div>

11. Если диапазоны неназначенных номеров расположены в требуемом порядке, щелкните **Фиксировать все**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Использование Windows PowerShell для настройки неназначенных телефонных номеров

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Используйте **New-CsUnassignedNumber** для создания нового диапазона неназначенных номеров. Используйте **Set-CsUnassignedNumber** для изменения существующего диапазона неназначенных номеров.
    
    <div>
    

    > [!TIP]  
    > Если имеются перекрывающиеся диапазоны и требуется, чтобы эти диапазоны применялись в определенном порядке, включите параметр Priority. В этом случае при звонке будет применяться диапазон, обладающий наибольшим приоритетом.

    
    </div>
    
    В командной строке выполните один из следующих действий:
    
      - Чтобы создать диапазон номеров для службы оповещения, выполните:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Или: чтобы создать диапазон номеров для автосекретаря единая система обмена сообщениями Exchange, выполните:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Пример:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    или
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    В следующем примере показывается, как можно изменить номера в существующем диапазоне неназначенных номеров:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление диапазона неназначенных номеров в Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New — CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set — CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get — CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

