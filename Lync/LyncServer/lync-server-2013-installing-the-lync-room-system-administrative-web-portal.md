---
title: 'Lync Server 2013: Установка веб-портала администрирования системы комнат Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24757a87279f64dd903ed4fdfb26169b606f899c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Установка веб-портала администрирования системы комнат Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-04-09_

Вы можете скачать веб-портал администрирования системы комнат Microsoft Lync из центра загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).

Чтобы установить веб-портал администрирования системы комнат Lync, выполните указанные ниже действия.

1.  Настройте порт доверенного приложения, выполнив следующий командлет в командной консоли Lync Server:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Чтобы установить портал "комната для собраний", скачайте **линкрумадминпортал. exe** , а затем запустите его от имени администратора.

3.  Откройте файл Web. config в следующем расположении:
    
    % Program Files\\% Microsoft Lync Server\\2013 веб\\-компонентов для\\Конференц\\-зала портал\\

4.  В файле Web. config замените Порталусернаме на имя пользователя, созданное на шаге 2 в разделе "Настройка предварительных требований для портала администрирования системы комнат Lync" (рекомендуемое имя в шаге — Lrsapp включена поддержка):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Так как портал администрирования LRS является доверенным приложением, вам не нужно указывать пароль в конфигурации портала. Если для этого пользователя используется другой регистратор, отличный от регистратора локального регистратора, необходимо указать для него регистратор, добавив следующую строку в файл Web. config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Если используется порт, отличный от 5061, добавьте в файл Web. config следующую строку:
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Проверка установки веб-портала администрирования системы комнат Lync

Чтобы проверить установку веб-портала администрирования системы комнат Lync, выполните следующие действия:


1.  На сервере переднего плана перейдите по следующему URL-адресу:
    
    https://\<Fe Server\>/ЛРС
    
    Не отображаются никакие ошибки, как показано на следующем рисунке:
    
    ![Экран входа на портал администрирования системы комнат Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Экран входа на портал администрирования системы комнат Lync")

2.  Если ошибки не отображаются, попробуйте получить доступ к следующему URL-адресу с любого другого компьютера в топологии:
    
    https://\<Fe Server\>/ЛРС
    
    Чтобы получить доступ к странице, необходимо добавить записи DNS, как описано в разделе "необходимые записи DNS для автоматического входа клиентов" [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).

</div>

</div>

<span> </span>

</div>

</div>

</div>

