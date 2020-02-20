---
title: 'Lync Server 2013: Назначение пользователям номеров для отправки групповых вызовов пользователям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 172a91c1a1417db6ffd938a48360c7d4bce3533c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Назначение номера группы для отправки звонков пользователям в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

После добавления номеров групп ответа групп в таблицу орбит парковки вызовов можно назначить группы пользователям. Используйте дополнительное средство дополнительного набора ресурсов для активации функций расширения (SEFAUtil), чтобы назначить группы ответа на звонки пользователям.

<div>


> [!NOTE]  
> В гибридном развертывании не назначайте группу группового ответа на звонки пользователям, размещенным в сети. Пользователи, размещенные в Интернете, не могут участвовать в групповой отправке звонков. Это значит, что их звонки не могут отвечать другим пользователям и они не могут отвечать на звонки другим пользователям.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Назначение группе группового ответа на звонки пользователю

1.  Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Пример:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>См. также


[Включение групповой отправки звонков для пользователей в Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Отключение групповой отправки вызовов для пользователей в Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

