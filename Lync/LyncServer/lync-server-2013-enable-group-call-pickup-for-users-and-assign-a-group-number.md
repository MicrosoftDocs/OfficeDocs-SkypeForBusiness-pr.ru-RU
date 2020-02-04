---
title: 'Lync Server 2013: разрешение группового приема для пользователей и назначение номера группы'
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
ms.openlocfilehash: a5ad9bbc6f5505e5778872a568bdbc80b3f7bf91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Включение отправки группового звонка для пользователей в Lync Server 2013 и назначение номера группы

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

После того как вы добавите номера групп для отправки звонков в таблицу "приостановить Звонок", вы назначаете номера групп для пользователей и включаете для них функцию отправки групп. Используйте вспомогательный набор ресурсов для активации дополнительных компонентов (Сефаутил), чтобы назначить групповые номера и включить функцию отправки групповых звонков.

<div>


> [!NOTE]  
> В гибридном развертывании не назначайте группу отправки группового звонка пользователям, которые находятся в сети. Пользователи, которые подключены к сети, не могут принимать участие в расправке групповых звонков. That is, their calls cannot be answered by other users, and they cannot answer calls to other users.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Назначение номера группы и включение отправки группового звонка для пользователя

1.  Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Например, чтобы назначить пользователю групповой номер 199, введите:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>См. также


[Отключение отправки группового вызова для пользователей в Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

