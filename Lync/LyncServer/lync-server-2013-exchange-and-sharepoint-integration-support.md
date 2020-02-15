---
title: 'Lync Server 2013: поддержка интеграции Exchange и SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 566af847bb177173f91634b9b46cceae1d9c88ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Поддержка интеграции Exchange и SharePoint в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-01-18_

Lync Server 2013 и Lync 2013 могут безопасно и эффективно взаимодействовать с другими приложениями и серверными продуктами, в том числе Office 2013, Exchange Server 2013, Exchange Server 2016 и SharePoint, если вы интегрируете эти продукты. Интеграция Lync Server 2013 и Office предоставляет пользователям доступ в контексте обмена мгновенными сообщениями, расширенных возможностей присутствия, телефонии и конференц-связи в Lync. Пользователи Office могут получать доступ к функциям Lync из клиента Outlook 2013 для обмена сообщениями и совместной работы, а также из других программ Office или из страницы SharePoint. Пользователи также могут просматривать записи бесед Lync в папке "Журнал бесед Outlook". При интеграции с Exchange 2013, Exchange 2016 или Exchange Online Lync Server 2013 также поддерживает следующие компоненты:

  - Единое хранилище контактов, которое позволяет пользователям хранить все контактные данные в Exchange или Exchange Online, чтобы информация была доступна глобально для Lync 2013, Exchange, Outlook и Outlook Web App.

  - Журнал бесед и история веб-конференций, которые хранятся в папках пользователей Exchange.

  - Архивированный контент из Lync, например, Обмен мгновенными сообщениями и контент собрания, можно хранить в хранилище Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 поддерживает интеграцию с предыдущими версиями Microsoft Exchange Server и SharePoint Server, но не все функции поддерживаются в этих предыдущих версиях, таких как интеграция хранилища архивации с Microsoft Exchange.<BR>Если вы переносите пользователей в Exchange 2013 или Exchange 2016, вы можете использовать как хранилище Exchange, так и хранилище Lync Server на промежуточной основе. Постоянное использование хранилища Exchange и сервера Lync Server не поддерживается.



</div>

Для интеграции Lync Server 2013 с Exchange Server и SharePoint Server требуется межсерверная проверка подлинности между серверами, работающими под управлением Lync Server 2013, Exchange Server и SharePoint Server. Lync Server 2013 поддерживает протокол OAuth (открытая авторизация) для проверки подлинности и авторизации "сервер-сервер". Для межсерверной проверки подлинности между двумя локальными серверами Майкрософт нет необходимости использовать сторонний сервер маркеров. Lync Server 2013, Exchange Server и SharePoint Server имеют встроенный сервер маркеров, который можно использовать в целях проверки подлинности. Например, Lync Server 2013 может выдать и подписать маркер безопасности самостоятельно и использовать этот маркер при взаимодействии с Exchange. В этом случае не нужно использовать сторонний сервер маркеров.

Lync Server 2013 поддерживает два сценария межсерверной проверки подлинности. К ним относятся Настройка межсерверной проверки подлинности между следующими серверами:

  - Локальная установка Lync Server 2013 и локальная установка Exchange Server 2013, Exchange Server 2016 и/или SharePoint Server.

  - Сочетание компонентов Office (например, между Microsoft Exchange 365 и Microsoft Lync Server 365 или между Microsoft Lync Server 365 и Microsoft SharePoint 365).

<div>


> [!NOTE]  
> Проверка подлинности между серверами между локальным сервером и компонентом Office 365 не поддерживается в этом выпуске Lync Server 2013. Помимо прочего, это означает, что невозможно настроить межсерверную проверку подлинности между локальной установкой Lync Server 2013 и Microsoft Exchange 365.



</div>

Дополнительные сведения о проверке подлинности между серверами можно найти в статье [Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по операциям.

</div>

<span> </span>

</div>

</div>

</div>

