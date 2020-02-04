---
title: 'Lync Server 2013: отключение отправки группового звонка для пользователей'
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
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Отключение отправки группового вызова для пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

Чтобы отключить функцию отправки группового звонка для пользователя, выполните указанные ниже действия.

<div>


> [!NOTE]  
> Если вы отключите функцию отправки группового звонка для пользователя, номер группы для отправки звонков, назначенный пользователю, не сохраняется. Если вы попытаетесь снова включить функцию отправки групп для этого пользователя, вы должны снова назначить номер группы для отправки звонков с помощью параметра/енаблеграуппиккуп.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>Отключение отправки группового звонка для пользователя

1.  Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Например:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение номеров группового звонка пользователям в Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Включение отправки группового звонка для пользователей в Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

