---
title: 'Lync Server 2013: разрешение группового приема звонков для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc2f513960371d0115b63260d35180f319bd923
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Включение отправки группового звонка для пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

С помощью средства Сефаутил Resource Kit вы можете включить функцию отправки групп для пользователей. Пользователи должны назначить номер группы с типом Грауппиккуп в таблице «орбита», чтобы включить функцию отправки группового звонка. Вы назначаете номер группы для отправки звонков и включаете возможность отправки группового звонка одновременно с помощью параметра/енаблеграуппиккуп при запуске Сефаутил. exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Включение отправки группового звонка для пользователя

1.  Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Например:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение номеров группового звонка пользователям в Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Отключение отправки группового вызова для пользователей в Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

