---
title: 'Lync Server 2013: отключение пользователя для корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0d2e5cf6eaa6ed594e7f5fbbc5b1e6a4c9103a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Отключение пользователя для корпоративной голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Используйте следующую процедуру, чтобы отключить корпоративную голосовую связь для учетной записи пользователя, для которой включена Lync Server 2013.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Отключение учетной записи пользователя для корпоративной голосовой связи

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Пользователи**.

4.  В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.

5.  В таблице щелкните учетную запись пользователя, для которой необходимо включить поддержку корпоративной голосовой связи.

6.  В меню **Изменить** щелкните **Показать сведения**.

7.  На странице **Изменение пользователя Lync Server** в разделе **Телефония** щелкните любой параметр, кроме **Корпоративная голосовая связь**.
    
    <div>
    

    > [!NOTE]  
    > Чтобы запретить пользователю совершать аудио-и видеовызовы с помощью Lync, в разделе <STRONG>телефония</STRONG>нажмите кнопку <STRONG>аудио/видео отключена</STRONG>.

    
    </div>

8.  Щелкните **Исполнить**.

Теперь пользователь не может использовать функцию корпоративной голосовой связи.

</div>

<div>

## <a name="see-also"></a>См. также


[Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Управление корпоративной голосовой связью для пользователей в Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

