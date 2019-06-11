---
title: 'Lync Server 2013: Установка системы управления комнатой на Lync Web портал'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c69231c6f07d2e57c0fe8be31d18ed6da109fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Installing the Lync Room System Administrative Web Portal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2015-04-09_

Вы можете скачать веб-портал для Microsoft Lync Room System из центра загрузки Майкрософт по адресу [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).

Чтобы установить веб-портал для управления комнатой на Lync, выполните указанные ниже действия.

1.  Настройте порт доверенного приложения, выполнив следующий командлет в командной консоли Lync Server.
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Чтобы установить портал комнаты для собраний, скачайте **линкрумадминпортал. exe** и запустите его в качестве администратора.

3.  Откройте файл Web.config в следующей папке:
    
    % Program Files\\% Microsoft Lync Server\\2013 веб\\-компоненты для\\собраний портал\\комнаты\\

4.  В файле Web. config измените Порталусернаме на имя пользователя, созданное на этапе 2, в разделе "Настройка предварительных требований для портала администрирования системы комнат в Lync" (рекомендуемое имя на этапе — Лрсапп):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Поскольку портал администрирования ЛРС является надежным приложением, вам не нужно указывать пароль в конфигурации портала. Если этот пользователь использует регистратор, отличный от локального, необходимо указать регистратор, добавив в файл Web.Config следующую строку:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Если используется порт, отличный от 5061, добавьте в файл Web.Config следующую строку: 
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Проверка установки системы управления комнатой Lync Web портал

Чтобы проверить, установлен ли веб-портал для управления комнатой на Lync, выполните указанные ниже действия.


1.  Откройте следующий URL-адрес на сервере переднего плана:
    
    https://\<Fe-Server\>/ЛРС
    
    При этом не должно выводиться никаких сообщений об ошибках, как на следующем рисунке:
    
    ![Экран входа в систему на портале администратора системы Lync в комнате] (images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Экран входа в систему на портале администратора системы Lync в комнате")

2.  Если никаких сообщений при этом не выводится, попробуйте перейти по следующему URL-адресу с любого другого компьютера в топологии:
    
    https://\<Fe-Server\>/ЛРС
    
    Для доступа к странице вам потребуется добавить записи DNS, как описано в разделе "необходимые записи DNS для автоматического входа в клиент" [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).

</div>

</div>

<span> </span>

</div>

</div>

</div>

