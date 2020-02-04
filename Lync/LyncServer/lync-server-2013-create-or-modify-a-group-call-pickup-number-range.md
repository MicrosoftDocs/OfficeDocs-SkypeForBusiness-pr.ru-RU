---
title: 'Lync Server 2013: создание или изменение диапазона номеров для отправки группового звонка'
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
ms.openlocfilehash: d5a644cb6008976894c88de570aa9cb6530e10c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Create or modify a Group Call Pickup number range in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

Воспользуйтесь следующей процедурой для создания или изменения диапазона номеров группы ответа на звонки в таблице орбит парковки вызовов.

<div>


> [!NOTE]  
> Вы должны использовать командную консоль Lync Server для создания, изменения, удаления и просмотра диапазонов номеров отправки групп в таблице "приостановить Звонок". На панели управления Lync Server не доступны диапазоны номеров для отправки групповых звонков.



</div>

<div>


> [!IMPORTANT]  
> Диапазон номеров группы для отправки звонков должен быть назначен типом Грауппиккуп. Пользователи могут расбирать групповые звонки только в том случае, если назначенный ей номер группы — Грауппиккуп.



</div>

Диапазоны номеров группы ответа на звонки должны соответствовать следующим правилам:

  - Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.

  - Длина начального номера диапазона должна такой же, как и у конечного номера диапазона.

  - Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.

  - Если диапазон номеров начинается с символа \* или \#диапазон должен быть больше 100.

  - Допустимые значения: должны соответствовать строке регулярного выражения\[\\\*|\#\](\[ ? 1-9\]\\г{0,7}.) | (\[1-9\]\\г{0,8}). Это означает, что значение должно быть строкой, начинающейся с \* символа \# или числом от 1 до 9 (первый символ не может равняться нулю). Если первый символ является \* числом \#от 1 до 9 (это значение не может равняться нулю), должен быть один из следующих знаков. Последующие символы могут быть числами от 0 до 9 до семи дополнительных символов (например, "\#6000", "\*92000", "\*95551212" и "915551212"). Если первый символ не \* \#является числом от 1 до 9 (он не может быть равен нулю), а затем содержит до восьми символов, каждый из чисел от 0 до 9 (например, "915551212", "41212", "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Создание или изменение диапазона номеров группы ответа на звонки

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Используйте командлет  **New-CsCallParkOrbit** для создания нового диапазона номеров группы ответа на звонки. Используйте командлет **Set-CsCallParkOrbit** для изменения существующего диапазона номеров ответа на звонки.
    
    В командной строке выполните следующую команду:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Например:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    Следующий пример показывает, как изменить диапазон номеров с орбит парковки вызовов на группы ответа на звонки.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Используйте этот командлет для изменения типа, назначенного диапазонам номеров, только в том случае, если вы изначально указали неправильный тип, а данный диапазон номеров группы пока не используется. Если изменить диапазон номеров с CallPark на GroupPickup или наоборот, когда этот диапазон уже используется, то для этого диапазона номеров будет прекращена работа компонента парковки вызовов или группового ответа на звонки. Например, если изменить диапазон номеров с Каллпарк на Грауппикк, приложение для парковки звонков больше не сможет использовать этот диапазон орбиты для приостановки звонка.

    
    </div>

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

