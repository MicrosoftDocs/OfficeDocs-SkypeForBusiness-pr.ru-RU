---
title: 'Lync Server 2013: поддержка Exchange и интеграции с SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4d378337643adf79557bd4bbb649a01948de27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Поддержка интеграции Exchange и SharePoint в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2017-01-18_

Lync Server 2013 и Lync 2013 могут безопасно и без проблем взаимодействовать с другими приложениями и серверными продуктами, в том числе с Office 2013, Exchange Server 2013, Exchange Server 2016 и SharePoint, если вы интегрируете эти продукты. Интеграция Lync Server 2013 и Office предоставляет пользователям доступ в контексте обмена мгновенными сообщениями, расширенных возможностей присутствия, телефонии и конференции в Lync. Пользователи Office могут получать доступ к функциям Lync из клиента Outlook 2013 для совместной работы, а также из другого приложения Office или со страницы SharePoint. Пользователи также могут просматривать записи бесед Lync в папке "Журнал бесед" Outlook. При интеграции с Exchange 2013, Exchange 2016 или Exchange Online сервер Lync Server 2013 также поддерживает следующие возможности:

  - Единое хранилище контактов, позволяющее пользователям хранить все контактные данные в Exchange или Exchange Online, чтобы они были доступны глобально в среде Lync 2013, Exchange, Outlook и Outlook Web App.

  - Журнал бесед и журнал веб-конференций, хранящийся в папках пользователя Exchange.

  - Архивированные данные из Lync, такие как обмен мгновенными сообщениями и контент собрания, могут храниться в хранилище Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 поддерживает интеграцию с предыдущими версиями Microsoft Exchange Server и SharePoint Server, но не все функции поддерживаются в предыдущих версиях, таких как интеграция хранилища архивов с Microsoft Exchange.<BR>Если вы переносите пользователей на Exchange 2013 или Exchange 2016, то во время миграции можно использовать как хранилище Exchange, так и хранилище сервера Lync Server. Постоянное использование хранилища Exchange и сервера Lync Server не поддерживается.



</div>

Для интеграции Lync Server 2013 в Exchange Server и SharePoint Server требуется проверка подлинности серверов между серверами с Lync Server 2013, Exchange Server и SharePoint Server. Lync Server 2013 поддерживает протокол OAuth (открытая авторизация) для проверки подлинности и авторизации сервера и сервера. Для проверки подлинности локальных серверов между двумя серверами Майкрософт нет необходимости в использовании стороннего сервера Token Server. У Lync Server 2013, Exchange Server и SharePoint Server есть встроенный сервер маркеров, который можно использовать для проверки подлинности друг с другом. Например, Lync Server 2013 может выпустить и подписать маркер безопасности самостоятельно и использовать этот маркер при общении с Exchange. В этом случае нет необходимости использовать сторонний сервер маркеров.

Lync Server 2013 поддерживает два сценария проверки подлинности между сервером и сервером. Сюда входят параметры проверки подлинности серверов и серверов между указанными ниже.

  - Локальная установка Lync Server 2013 и локальная установка Exchange Server 2013, Exchange Server 2016 и (или) SharePoint Server.

  - Пара компонентов Office (например, между Microsoft Exchange 365 и Microsoft Lync Server 365 или между Microsoft Lync Server 365 и Microsoft SharePoint 365).

<div>


> [!NOTE]  
> Проверка подлинности "сервер-сервер" между локальным сервером и компонентом Office 365 не поддерживается в этом выпуске Lync Server 2013. Помимо прочего, это означает, что вы не можете настроить проверку подлинности между сервером между локальной установкой Lync Server 2013 и Microsoft Exchange 365.



</div>

Подробнее о проверке подлинности серверов и серверов можно найти в разделе Управление проверкой подлинности серверов [(OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по операциям.

</div>

<span> </span>

</div>

</div>

</div>

