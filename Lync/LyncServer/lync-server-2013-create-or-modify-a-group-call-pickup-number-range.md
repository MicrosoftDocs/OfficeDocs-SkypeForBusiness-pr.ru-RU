---
title: 'Lync Server 2013: создание или изменение диапазона номеров для группового ответа на звонки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee394401999038c205826c99b3e6b2e35734087d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506136"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Создание или изменение диапазона номеров для группового ответа на звонки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Используйте следующую процедуру для создания или изменения диапазона номеров группы ответа на звонки в таблице орбит парковки вызовов.

<div>


> [!NOTE]  
> Для создания, изменения, удаления и просмотра групп номеров для ответа на звонки в таблице орбит парковки вызовов необходимо использовать командную консоль Lync Server. Диапазоны номеров для группового ответа на звонки недоступны в панели управления Lync Server.



</div>

<div>


> [!IMPORTANT]  
> Диапазону номеров группы ответа на звонки должен быть назначен тип Грауппиккуп. Пользователи могут получать групповые звонки только в том случае, если номер группы, которым она назначена, имеет тип Грауппиккуп.



</div>

Диапазоны номеров группы ответа на звонки должны соответствовать следующим правилам:

  - Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.

  - Значение начального номера диапазона должно иметь такую же длину, что и конечный номер диапазона.

  - Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.

  - Если диапазон номеров начинается с символа \* или \# , диапазон должен быть больше 100.

  - Допустимые значения: должны быть согласованы со строкой регулярного выражения ( \[ \\ \* | \# \] ? \[ 1-9 \] \\ d {0,7} ) | ( \[ 1-9 \] \\ d {0,8} ). Это означает, что значение должно быть строкой, начинающейся с символа \* или \# цифры от 1 до 9 (первый символ не может быть нулевым). Если первый символ является \* или \# , то следующий символ должен быть цифрой от 1 до 9 (он не может быть нулевым). Последующими символами могут быть цифры от 0 до 9 до семи дополнительных символов (например, " \# 6000", " \* 92000", " \* 95551212" и "915551212"). Если первый символ не \* или \# , то первым символом должен быть цифра от 1 до 9 (он не может быть равен нулю), а должен содержать до восьми символов, каждый из которых имеет цифру от 0 до 9 (например, "915551212", "41212", "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Создание или изменение диапазона группы ответа на звонки

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Используйте **New – CsCallParkOrbit** для создания нового диапазона номеров группы ответа на звонки. Используйте **Set – CsCallParkOrbit** , чтобы изменить существующий диапазон номеров для ответа на звонки.
    
    В командной строке выполните следующую команду:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Пример:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    В приведенном ниже примере показано, как изменить диапазон номеров с орбит парковки вызовов на группы ответа на звонки.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Используйте этот командлет для изменения типа, назначенного для диапазонов номеров, только в том случае, если изначально указан неверный тип, а диапазон групп еще не используется. Если вы изменяете диапазон номеров с CallPark на Грауппиккуп или наоборот, а диапазон номеров уже используется, то для этого диапазона номеров будет прекращена работа приостановки вызовов или групповой отправки звонков. Например, если изменить диапазон номеров с CallPark на Грауппикк, то приложение парковки вызовов больше не сможет использовать этот диапазон орбит для парковки вызовов.

    
    </div>

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

