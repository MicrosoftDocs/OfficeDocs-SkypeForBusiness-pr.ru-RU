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
ms.openlocfilehash: fb7e35b9347cc38239df7d2e28ddeda05e86cda5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Настройка интеграции с сервером Office Web Apps и Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-08-19_

Lync Server 2013 использует сервер Office Web Apps для обработки презентаций PowerPoint. Дополнительные сведения о преимуществах этого подхода приведены в статье [Обзор веб-конференций в Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Чтобы использовать эти новые возможности, администраторы должны установить сервер Office Web Apps, и они должны настроить Lync Server 2013 для связи с сервером Office Web Apps. В этой документации представлены сведения о том, как настроить Lync Server 2013 для работы с сервером Office Web Apps. Сведения о том, как установить сервер Office Web Apps, не предоставляются в документации. для получения этих сведений посетите веб-сайт развертывания Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>по адресу. Это руководство включает полную информацию о предварительных требованиях для сервера Office Web Apps; Обратите внимание на то, что сервер Office Web Apps должен быть установлен на автономном компьютере, на котором не работает Lync Server, Microsoft SQL Server или другое серверное приложение. (На компьютере не должна быть установлена какая-либо версия Microsoft Office.) На любом компьютере, используемом для запуска Office Web Apps, также должен быть установлен определенный набор программного обеспечения (включая .NET Framework 4,5 и Windows PowerShell 3,0); Эти требования, а также сведения о настройке сертификатов и служб IIS, подробно обсуждаются на веб-сайте развертывания Microsoft Office Web Apps по адресу <http://go.microsoft.com/fwlink/p/?linkid=257525>.

<div>


> [!NOTE]  
> Последняя итерация сервер Office Web Apps называется Office Online Server, которая поддерживается в Lync Server 2013. Более подробную информацию можно найти в <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">документации по Office Online Server</A>.



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

