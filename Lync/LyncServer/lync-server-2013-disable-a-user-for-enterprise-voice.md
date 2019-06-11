---
title: 'Lync Server 2013: отключение пользователя для корпоративного голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dabe378f07cbca263ba3b32257c310b01bd922c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Отключение пользователя для корпоративного голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Чтобы отключить корпоративную голосовую почту для учетной записи пользователя, доступной для Lync Server 2013, выполните указанные ниже действия.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Отключение учетной записи пользователя для корпоративной голосовой связи

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Пользователи**.

4.  В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.

5.  В таблице выберите учетную запись пользователя, которую вы хотите включить для корпоративного голосовой связи.

6.  В меню **Правка** щелкните **Подробнее**.

7.  На странице " **изменение пользователя Lync Server** " в разделе **телефония**выберите любой параметр, кроме **корпоративных голосовых сообщений**.
    
    <div>
    

    > [!NOTE]  
    > Чтобы запретить пользователю выполнять голосовые и видеозвонки с помощью Lync, в разделе <STRONG>телефония</STRONG>выберите пункт <STRONG>звук и видео отключен</STRONG>.

    
    </div>

8.  Нажмите **Исполнить**.

Теперь пользователь не может использовать функцию голосовой связи в корпоративной среде.

</div>

<div>

## <a name="see-also"></a>См. также


[Включение пользователей корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Управление корпоративной голосовой связью для пользователей в Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[командная консоль Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

