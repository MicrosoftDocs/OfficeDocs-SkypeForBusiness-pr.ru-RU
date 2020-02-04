---
title: 'Lync Server 2013: Назначение пользователям номеров для отправки групповых звонков'
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
ms.openlocfilehash: e65eef9fcf425ad8ea9f36dc57899bb6af924bf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Назначение номеров группового звонка пользователям в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

После добавления номеров групп отправки группового звонка в таблицу "приостановить Звонок" можно назначить группы пользователям. Используйте вспомогательный набор ресурсов для активации дополнительных функций расширения (Сефаутил), чтобы назначить пользователям группы для отправки звонков.

<div>


> [!NOTE]  
> В гибридном развертывании не назначайте группу отправки группового звонка пользователям, которые находятся в сети. Пользователи, которые подключены к сети, не могут принимать участие в расправке групповых звонков. That is, their calls cannot be answered by other users, and they cannot answer calls to other users.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Назначение группе отправки группового звонка пользователю

1.  Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Например:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>См. также


[Включение отправки группового звонка для пользователей в Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Отключение отправки группового вызова для пользователей в Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

