---
title: 'Lync Server 2013: отключение отправки группового ответа на звонки для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3e015fd7fc3be36439fb240e2f3f50ed7bc8ec1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Отключение групповой отправки вызовов для пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Используйте следующую процедуру для отключения групповой отправки звонков для пользователя.

<div>


> [!NOTE]  
> Когда вы отключаете групповой ответ на звонки для пользователя, номер группы ответа на звонки, назначенный пользователю, не сохраняется. Если вы попытаетесь повторно включить запрос групп для этого пользователя, необходимо снова назначить номер группы ответа на звонки с помощью параметра/енаблеграуппиккуп.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>Отключение групповой отправки вызовов для пользователя

1.  Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Пример:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение номера группы для отправки звонков пользователям в Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Включение групповой отправки звонков для пользователей в Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

