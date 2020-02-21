---
title: 'Lync Server 2013: Настройка среды для веб-портала администрирования системы комнат Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5198416e3c06dfd83cf7d1cf5bf3c6002ebe72ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Настройка среды Lync Server 2013 для веб-портала администрирования системы комнат Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-22_

Для использования веб-портала администрирования системы комнат Lync (LRS) необходимо установить или настроить следующие предварительные требования.

<div>


> [!IMPORTANT]  
> Если на сервере настроена проверка подлинности Kerberos и NTLM, а LRS запущен на компьютере, который не присоединен к домену, проверка подлинности Kerberos не будет выполнена, а пользователь не увидит состояние LRS на административном портале. Чтобы устранить эту проблему, настройте сервер с проверкой подлинности NTLM или проверкой подлинности NTLM и TLS-ДСК (без Kerberos) или Присоедините компьютер LRS к домену.



</div>

1.  Установка накопительных обновлений для Lync Server 2013:2013 июля в топологии Lync Server.
    
    Чтобы получить обновление или просмотреть сведения о том, что входит в состав этого приложения, ознакомьтесь со статьей [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Создайте пользователя Active Directory с включенной поддержкой SIP.
    
    Веб-портал администрирования LRS использует эти учетные данные для запроса информации из Lync Server. Рекомендуемое имя пользователя — Lrsapp включена поддержка.

3.  Создайте группу безопасности Active Directory с именем LRSSupportAdminGroup.
    
    Создайте группу с областью действия групп в качестве глобальной и типа группы как безопасность. Пользователи с включенной поддержкой SIP, добавленные в эту группу, будут авторизованы для просмотра списка помещений и выполнения определенных команд, например сбора журналов.

4.  Создайте группу безопасности Active Directory с именем LRSFullAccessAdminGroup.
    
    Создайте группу с областью действия групп в качестве глобальной и типа группы в качестве Security. пользователи с включенной поддержкой SIP, добавленные в эту группу, имеют право на использование всех функций портала администрирования.
    
     
    
    ![Список групп администраторов с ролью группы безопасности](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Список групп администраторов с ролью группы безопасности")  
    
     

5.  Добавьте LRSFullAccessAdminGroup в качестве члена LRSSupportAdminGroup.
    
    ![Страница "элементы свойств LRSSupportAdminGroup"](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Страница "элементы свойств LRSSupportAdminGroup"")  
    
     

6.  Создайте пользователя с включенной поддержкой SIP Active Directory с именем LRSSupport. Добавьте этого пользователя в LRSSupportAdminGroup.
    
    ![Страница "элементы свойств LRSSupportAdminGroup"](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Страница "элементы свойств LRSSupportAdminGroup"")  
    
     

7.  Установите ASP.NET MVC 4 для Visual Studio 2010 с пакетом обновления 1 (SP1) и Visual Web Developer 2010 SP1, [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967)который доступен в центре загрузки Майкрософт по адресу.

</div>

<span> </span>

</div>

</div>

</div>

