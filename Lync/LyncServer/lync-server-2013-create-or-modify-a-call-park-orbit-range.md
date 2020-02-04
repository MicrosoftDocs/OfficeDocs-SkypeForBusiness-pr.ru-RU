---
title: 'Lync Server 2013: создание или изменение диапазона на расстоянии по орбите'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf215caacd0e380a14429bd2d34791048878fc96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Создание или изменение диапазона орбиты на расстоянии вверх на сервере Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Используйте одну из следующих процедур для создания или изменения диапазона парковки вызовов.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Создание и изменение диапазона номеров для вызовов парковки с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева щелкните пункт **Функции голосовой связи**, а затем щелкните **Парковка вызовов**.

4.  На странице **Парковка вызовов** выполните одно из указанных ниже действий.
    
      - Чтобы создать новый диапазон орбиты, щелкните **Создать**. В поле **Имя** введите имя, определяющее этот диапазон номеров.
        
        <div>
        

        > [!NOTE]  
        > После фиксации диапазона орбиты в базе данных, это имя невозможно изменить.

        
        </div>
    
      - Чтобы изменить существующий диапазон орбиты, введите все части имени диапазона орбиты в поле поиска. В списке результатов орбит щелкните нужную орбиту, щелкните **Изменить**, затем **Подробнее**.

5.  В первом поле **Диапазон номеров** введите начальный номер диапазона добавочных номеров для этой орбиты парковки вызовов, а во втором поле **Диапазон номеров** введите конечный номер диапазона.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</P>
    > <LI>
    > <P>Длина начального номера диапазона должна такой же, как и у конечного номера диапазона.</P>
    > <LI>
    > <P>Диапазон орбит должен быть уникальным. Он не может пересекаться с другими диапазонами.</P>
    > <LI>
    > <P>Если диапазон орбит начинается с символа "*" или "#", диапазон должен быть больше 100.</P>
    > <LI>
    > <P>Допустимые значения: должны соответствовать строке регулярного выражения (\*[| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Это означает, что значение должно быть строкой, начинающейся с символа *, # или с цифры от 1 до 9 (первый символ не должен быть нулем). Если первый символ * или #, то следующий символ должен быть цифрой от 1 до 9 (он не может быть нулем). Последующие символы могут быть числами от 0 до 9 до семи дополнительных символов (например, "#6000", "*92000", "* 95551212" и "915551212"). Если же первый символ не "*" или "#", первым символом должна быть цифра в диапазоне от 1 до 9 (ноль не допускается), за которой следуют до восьми цифр в диапазоне от 0 до 9 (например: "915551212", "41212", "300").</P>
    > <LI>
    > <P>Всего для пула не должно быть более 50000 орбит. Каждый диапазон орбит обычно охватывает 100 или меньше орбит, но это число может быть намного больше, но не может превышать 10000. Например, вместо указания начального номера "7000000" и конечного номера "8000000" попробуйте задать начальный номер "7000000" и конечный номер "7000100".</P></LI></UL>

    
    </div>

6.  В качестве полного доменного **имени сервера назначения**выберите полное доменное имя (FQDN) или идентификатор службы приложения, на котором размещается приложение для парковки звонков. Все припаркованные звонки на номера в пределах диапазона, заданного начальным и конечным номером в диапазоне орбит, будет направляться на этот сервер или пул.

7.  Нажмите **Исполнить**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Использование Windows PowerShell для создания и изменения диапазона номеров для вызовов парковки

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Используйте командлет **New-CsCallParkOrbit** для создания нового диапазона номеров орбиты. Используйте командлет **Set-CsCallParkOrbit** для изменения существующего диапазона номеров орбиты.
    
    В командной строке выполните следующую команду:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Например:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    В приведенном ниже примере показано, как изменять номера в существующем диапазоне орбиты.
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление диапазона орбиты на расстоянии вверх на сервере Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

