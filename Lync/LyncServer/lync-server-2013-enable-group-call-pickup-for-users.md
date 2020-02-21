---
title: 'Lync Server 2013: Включение групповой отправки звонков для пользователей'
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
ms.openlocfilehash: 5842a22d1899398b282e7305e4dd921fea86ea39
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Включение групповой отправки звонков для пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Использование средства SEFAUtil Resource Kit для включения групповой отправки звонков для пользователей. Пользователям должен быть назначен номер группы с типом Грауппиккуп в таблице орбит парковки вызовов для включения групповой отправки звонков. Вы назначаете номер группы ответа на звонки и включаете запрос групп в то же время, используя параметр/енаблеграуппиккуп при запуске SEFAUtil. exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Включение групповой отправки звонков для пользователя

1.  Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.

2.  В командной строке выполните следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Пример:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение номера группы для отправки звонков пользователям в Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Отключение групповой отправки вызовов для пользователей в Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

