---
title: 'Lync Server 2013: создание или изменение диапазона орбит для парковки вызовов'
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
ms.openlocfilehash: e1ecf0a1313519a74bb054c7fa3b441580758018
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514786"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Используйте одну из следующих процедур для создания или изменения диапазона парковки вызовов.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Создание или изменение диапазона номеров для вызовов парковки с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации выберите **Компоненты голосовой связи**, а затем щелкните **Парковка вызовов**.

4.  На странице **Парковка вызовов** выполните одно из следующих действий.
    
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
    > <P>Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</P>
    > <LI>
    > <P>Длина значений начального и конечного номеров диапазона должна быть одинаковой.</P>
    > <LI>
    > <P>Диапазон орбиты должен быть уникальным и не должен перекрываться ни с одним другим диапазоном.</P>
    > <LI>
    > <P>Если диапазон орбиты начинается с символа * или #, то диапазон должен быть больше 100.</P>
    > <LI>
    > <P>Допустимые значения: должны быть согласованы со строкой регулярного выражения ([ \* | #]? [ 1-9] \d {0,7} ) | ([1-9] \d {0,8} ). Это означает, что значение должно представлять собою строку, которая начинается с символа "*" или "#" либо с цифры в диапазоне от 1 до 9 (первым символом не может быть нуль). Если первым символом является "*" или "#", за ним должна следовать цифра в диапазоне от 1 до 9 (опять же, не нуль). Последующими символами могут быть цифры от 0 до 9 до семи дополнительных символов (например, "#6000", "*92000", "* 95551212" и "915551212"). Если же первым символом не является "*" или "#", первым символом должна являться цифра в диапазоне от 1 до 9 (нуль не допускается), за которой следуют до восьми цифр в диапазоне от 0 до 9 (например:  "915551212", "41212", "300").</P>
    > <LI>
    > <P>В пуле не должно быть более 50 000 орбит. Каждый диапазон орбиты обычно включает не более 100 орбит, но может быть гораздо больше, до 10 000 орбит. Например, вместо указания начального номера "7000000" и конечного номера  "8000000" рекомендуется указывать начальный номер "7000000" и конечный номер "7000100".</P></LI></UL>

    
    </div>

6.  В поле **Полное доменное имя сервера назначения** выберите полное доменное имя или идентификатор службы приложений, где размещается приложение парковки вызовов. Все вызовы, припаркованные по номерам в диапазоне, заданном начальным и конечным номерами диапазона орбиты, будут маршрутизироваться на этот сервер или в этот пул.

7.  Нажмите кнопку **Зафиксировать**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Использование Windows PowerShell для создания или изменения диапазона номеров для вызовов парковки

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Используйте командлет **New-CsCallParkOrbit** для создания нового диапазона номеров орбиты. Используйте командлет **Set-CsCallParkOrbit** для изменения существующего диапазона номеров орбиты.
    
    В командной строке выполните следующую команду:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Пример:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    В приведенном ниже примере показано, как изменять номера в существующем диапазоне орбиты.
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление диапазона орбит парковки вызовов в Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New — CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set — CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

