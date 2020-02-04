---
title: 'Lync Server 2013: включение сервера Office Web Apps и Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37715182ba704f71bad463044ec9b47cea8f777b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Настройка интеграции с сервером Office Web Apps и Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-08-19_

Lync Server 2013 использует сервер Office Web Apps для обработки презентаций PowerPoint. Дополнительные сведения о преимуществах этого подхода можно найти [в статье Обзор веб-конференций в Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Для использования этих новых возможностей администраторы должны установить Office Web Apps Server, и они должны настроить Lync Server 2013 для взаимодействия с сервером Office Web Apps. В этой документации содержатся сведения о том, как настроить Lync Server 2013 для работы с сервером Office Web Apps. Сведения о том, что эта документация не содержит, — информация об установке сервера Office Web Apps. Эти сведения можно найти на веб-сайте развертывания Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>по адресу. В этом руководстве содержатся полные сведения о предварительных требованиях для сервера Office Web Apps. Обратите внимание на то, что сервер Office Web Apps необходимо установить на отдельном компьютере, на котором не запущен Lync Server, Microsoft SQL Server или другое серверное приложение. (На компьютере должна быть установлена какая-либо версия Microsoft Office.) На любом компьютере, который использовался для запуска Office Web Apps, должен быть установлен определенный набор программного обеспечения (включая .NET Framework 4,5 и Windows PowerShell 3,0); Эти требования, а также сведения о настройке сертификатов и информационных служб Интернета (IIS) подробно описаны на веб-сайте развертывания Microsoft Office Web Apps по адресу <http://go.microsoft.com/fwlink/p/?linkid=257525>.

<div>


> [!NOTE]  
> Для последней итерации сервера Office Web Apps используется сервер Office Online, который поддерживается приложением Lync Server 2013. Дополнительные сведения можно найти в документации по <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">серверу Office Online</A>.



</div>

В этом документе рассматриваются следующие темы:

  - [Настройка Lync Server 2013 для работы с сервером Office Web Apps](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Публикация сервера Office Web Apps в Lync Server 2013 с помощью обратного прокси-сервера](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Проверка конфигурации сервера Office Web Apps в Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Настройка клиентов Lync Server 2013 для использования с сервером Office Web Apps](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

