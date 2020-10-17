---
title: 'Lync Server 2013: включение сервера Office Web Apps и Lync Server 2013'
description: 'Lync Server 2013: включение сервера Office Web Apps и Lync Server 2013.'
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
ms.openlocfilehash: a1bf4e09dc29bf344b78df50595258f0663cd731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546525"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="6fbac-103">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fbac-103">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fbac-104">_**Последнее изменение темы:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="6fbac-104">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="6fbac-105">Lync Server 2013 использует сервер Office Web Apps для обработки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6fbac-105">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="6fbac-106">Дополнительные сведения о преимуществах этого подхода приведены в статье [Обзор веб-конференций в Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6fbac-106">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="6fbac-107">Чтобы использовать эти новые возможности, администраторы должны установить сервер Office Web Apps, и они должны настроить Lync Server 2013 для связи с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="6fbac-107">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="6fbac-108">В этой документации представлены сведения о том, как настроить Lync Server 2013 для работы с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="6fbac-108">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="6fbac-109">Сведения о том, как установить сервер Office Web Apps, не предоставляются в документации. для получения этих сведений посетите веб-сайт развертывания Microsoft Office Web Apps по адресу <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="6fbac-109">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="6fbac-110">Это руководство включает полную информацию о предварительных требованиях для сервера Office Web Apps; Обратите внимание на то, что сервер Office Web Apps должен быть установлен на автономном компьютере, на котором не работает Lync Server, Microsoft SQL Server или другое серверное приложение.</span><span class="sxs-lookup"><span data-stu-id="6fbac-110">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="6fbac-111">(На компьютере не должна быть установлена какая-либо версия Microsoft Office.) На любом компьютере, используемом для запуска Office Web Apps, также должен быть установлен определенный набор программного обеспечения (включая .NET Framework 4,5 и Windows PowerShell 3,0); Эти требования, а также сведения о настройке сертификатов и служб IIS, подробно обсуждаются на веб-сайте развертывания Microsoft Office Web Apps по адресу <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="6fbac-111">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fbac-112">Последняя итерация сервер Office Web Apps называется Office Online Server, которая поддерживается в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbac-112">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="6fbac-113">Более подробную информацию можно найти в <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">документации по Office Online Server</A>.</span><span class="sxs-lookup"><span data-stu-id="6fbac-113">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="6fbac-114">В этом документе рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="6fbac-114">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="6fbac-115">Настройка Lync Server 2013 для работы с сервером Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="6fbac-115">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="6fbac-116">Публикация сервера Office Web Apps в Lync Server 2013 с помощью обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="6fbac-116">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="6fbac-117">Проверка конфигурации сервера Office Web Apps в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fbac-117">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="6fbac-118">Настройка клиентов Lync Server 2013 для использования с сервером Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="6fbac-118">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

