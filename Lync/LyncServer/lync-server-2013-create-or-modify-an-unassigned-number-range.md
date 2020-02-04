---
title: 'Lync Server 2013: создание или изменение неназначенного диапазона номеров'
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
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Создание и изменение неназначенного диапазона номеров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Используйте одну из описанных ниже процедур для настройки диапазонов номеров, неназначенных для приложения извещения.

<div>


> [!IMPORTANT]  
> Перед настройкой таблицы неназначенные номера необходимо предварительно определить одно или несколько объявлений или настроить автосекретарь единой системы обмена сообщениями Exchange.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Настройка неназначенных телефонных номеров с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните **Функции голосовой связи**, затем **Неназначенный номер**.

4.  На странице **Неназначенный номер** выполните одно из следующих действий.
    
      - Для создания нового диапазона номеров щелкните **Создать**. В поле **Имя** введите идентификационное имя этого диапазона номеров.
        
        <div>
        

        > [!NOTE]  
        > После записи нового диапазона неназначенных номеров в базе данных вы не сможете изменить имя диапазона.

        
        </div>
    
      - Для изменения существующего диапазона номеров полностью или частично введите его имя в поле поиска. В сформированном списке найденных диапазонов номеров щелкните требуемое имя и выберите **Изменить**, затем **Подробнее**.

5.  В первом поле **Диапазон номеров** введите начальный номер диапазона, а во втором поле **Диапазон номеров** введите его конечный номер.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</P>
    > <LI>
    > <P>Если первый номер или последний номер диапазона содержит добавочный номер, то оба номера (первый и последний) должны содержать добавочный номер. Кроме того, добавочный номер должен быть одинаковым для первого и последнего номера диапазона.</P>
    > <LI>
    > <P>Номер должен соответствовать регулярному выражению (Tel:) ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?. Это означает, что номер должен начинаться со строки "tel:" (если эта строка не указана, она будет добавлена автоматически), знака "плюс" (+) и цифры от 1 до 9. Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</P></LI></UL>

    
    </div>

6.  В поле **Служба оповещения** выполните одно из следующих действий.
    
      - Щелкните **Оповещение**.
    
      - Щелкните **Единая система обмена сообщениями Exchange**.

7.  Если на предыдущем шаге выбран вариант **Оповещение**, выполните следующие действия.
    
    1.  В разделе **полное доменное имя целевого сервера**нажмите кнопку **выбрать**, выберите идентификатор службы приложения, на котором будет выполняться объявление для обработки входящих звонков с этим диапазоном неназначенных номеров, и нажмите кнопку **ОК**.
    
    2.  В разделе **Оповещение** выберите оповещение, которое требуется воспроизводить для даннго диапазона неназначенных номеров.

8.  Если на предыдущем шаге выбран вариант **Единая система обмена сообщениями Exchange**, в разделе **Номер автосекретаря** щелкните **Выбрать**, выберите номер телефона для данного диапазона неназначенных номеров, затем нажмите кнопку **ОК**.

9.  Нажмите **ОК**.

10. Убедитесь в том, что на странице **Неназначенный номер** диапазоны неназначенных номеров расположены в требуемом порядке. Для изменения места диапазона в таблице выберите одно или несколько смежных имен в списке диапазонов, затем щелкните стрелку вверх или вниз.
    
    <div>
    

    > [!TIP]  
    > Lync Server ищет в таблице неназначенные номера сверху вниз и использует первый диапазон, который соответствует неназначенному номеру. Если при наличии перекрывающихся диапазонов один диапазон задает действие, которое служит последним средством, убедитесь в том, что этот диапазон находится внизу списка.

    
    </div>

11. Расположив диапазоны неназначенных номеров в требуемом порядке, щелкните **Выбрать все**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Использование Windows PowerShell для настройки неназначенных телефонных номеров

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Используйте **New-ксунассигнеднумбер** для создания нового неназначенного диапазона номеров. С помощью **Set-ксунассигнеднумбер** можно изменить существующий диапазон номеров, отличный от назначенного.
    
    <div>
    

    > [!TIP]  
    > Если имеются перекрывающиеся диапазоны и требуется, чтобы эти диапазоны применялись в определенном порядке, включите параметр Priority. В этом случае при звонке будет применяться диапазон, обладающий наибольшим приоритетом.

    
    </div>
    
    В командной строке выполните один из следующих действий:
    
      - Чтобы создать диапазон номеров для службы оповещения, выполните:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Или: чтобы создать диапазон номеров для автосекретаря единая система обмена сообщениями Exchange, выполните:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Например:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    Или
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    В следующем примере показывается, как можно изменить номера в существующем диапазоне неназначенных номеров:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление неназначенного диапазона номеров в Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

