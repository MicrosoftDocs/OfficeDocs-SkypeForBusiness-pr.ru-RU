---
title: 'Lync Server 2013: Включение групповой отправки звонков для пользователей и назначение номера группы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c541d5a82becf253ebbbb2bbab6d1c69e9fb7016
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Включение групповой отправки звонков для пользователей в Lync Server 2013 и назначение номера группы

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

После добавления номеров групп ответа на звонки в таблицу орбит парковки вызовов необходимо назначить номера групп пользователям и включить для них функцию отправки групп. Используйте дополнительное средство дополнительного набора ресурсов для активации дополнительных компонентов (SEFAUtil), чтобы назначить номера групп и включить отправке звонков групп.

<div>


> [!NOTE]  
> В гибридном развертывании не назначайте группу группового ответа на звонки пользователям, размещенным в сети. Пользователи, размещенные в Интернете, не могут участвовать в групповой отправке звонков. Это значит, что их звонки не могут отвечать другим пользователям и они не могут отвечать на звонки другим пользователям.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Назначение номера группы и включение групповой отправки звонков для пользователя

1.  Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Например, чтобы назначить пользователю номер группы 199, выполните указанные ниже действия.
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>См. также


[Отключение групповой отправки вызовов для пользователей в Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

