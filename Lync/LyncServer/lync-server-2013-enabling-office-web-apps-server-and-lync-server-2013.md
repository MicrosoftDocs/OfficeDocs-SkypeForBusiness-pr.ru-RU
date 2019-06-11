---
title: 'Lync Server 2013: включение сервера Office Web Apps и Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a88a9a1649d8842c9c2c4a1f55aefcfc7853e05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="47d0a-102">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47d0a-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47d0a-103">_**Тема последнего изменения:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="47d0a-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="47d0a-104">Lync Server 2013 использует сервер Office Web Apps для обработки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="47d0a-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="47d0a-105">Дополнительные сведения о преимуществах этого подхода можно найти [в статье Обзор веб-конференций в Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="47d0a-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="47d0a-106">Для использования этих новых возможностей администраторы должны установить Office Web Apps Server, и они должны настроить Lync Server 2013 для взаимодействия с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="47d0a-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="47d0a-107">В этой документации содержатся сведения о том, как настроить Lync Server 2013 для работы с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="47d0a-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="47d0a-108">Сведения о том, что эта документация не содержит, — информация об установке сервера Office Web Apps. Эти сведения можно найти на веб-сайте развертывания Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>по адресу.</span><span class="sxs-lookup"><span data-stu-id="47d0a-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="47d0a-109">В этом руководстве содержатся полные сведения о предварительных требованиях для сервера Office Web Apps. Обратите внимание на то, что сервер Office Web Apps необходимо установить на отдельном компьютере, на котором не запущен Lync Server, Microsoft SQL Server или другое серверное приложение.</span><span class="sxs-lookup"><span data-stu-id="47d0a-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="47d0a-110">(На компьютере должна быть установлена какая-либо версия Microsoft Office.) На любом компьютере, который использовался для запуска Office Web Apps, должен быть установлен определенный набор программного обеспечения (включая .NET Framework 4,5 и Windows PowerShell 3,0); Эти требования, а также сведения о настройке сертификатов и информационных служб Интернета (IIS) подробно описаны на веб-сайте развертывания Microsoft Office Web Apps по адресу <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span><span class="sxs-lookup"><span data-stu-id="47d0a-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47d0a-111">Для последней итерации сервера Office Web Apps используется сервер Office Online, который поддерживается приложением Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47d0a-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="47d0a-112">Дополнительные сведения можно найти в документации по <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">серверу Office Online</A>.</span><span class="sxs-lookup"><span data-stu-id="47d0a-112">For more detail, refer to the <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="47d0a-113">В этом документе рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="47d0a-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="47d0a-114">Настройка Lync Server 2013 для работы с сервером Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="47d0a-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="47d0a-115">Публикация сервера Office Web Apps в Lync Server 2013 с помощью обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="47d0a-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="47d0a-116">Проверка конфигурации сервера Office Web Apps в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47d0a-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="47d0a-117">Настройка клиентов Lync Server 2013 для использования с сервером Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="47d0a-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

