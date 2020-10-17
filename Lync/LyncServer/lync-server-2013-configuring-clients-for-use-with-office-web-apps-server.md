---
title: 'Lync Server 2013: Настройка клиентов для использования с сервером Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf46a16d38e37dd8faac39a438053dcc7b8c103
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537066"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="f7a21-102">Настройка клиентов Lync Server 2013 для использования с сервером Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f7a21-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a21-103">_**Последнее изменение темы:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="f7a21-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="f7a21-104">Если вы хотите, чтобы пользователи выполнить все возможности сервера Office Web App, необходимо обновить эти пользователи до Microsoft Lync 2013; только пользователи Lync 2013 смогут выполнять такие задачи, как прокручивать слайды PowerPoint независимо от реальной презентации PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f7a21-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="f7a21-105">(То есть эти пользователи могут просматривать любой слайд в презентации в любое время, не мешая реальным презентациям.) Пользователи, не использующие Lync 2013, по-прежнему смогут присоединяться к конференциям и просматривать презентацию PowerPoint; Однако они не смогут независимо прокручивать слайды и не могут просматривать переходы слайдов и просматривать внедренные видеозаписи.</span><span class="sxs-lookup"><span data-stu-id="f7a21-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="f7a21-106">Обратите внимание, что эти возможности всегда будут доступны пользователям Lync 2013; Это справедливо даже в том случае, если у докладчика PowerPoint работает с Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="f7a21-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="f7a21-107">Если презентация PowerPoint размещается пользователем Lync 2010, Lync Server 2013 будет согласовываться с сервером Office Web Apps, чтобы пользователи Lync 2013 могли просматривать версию этой презентации на сервере Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="f7a21-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="f7a21-108">Сервер Office Web Apps не предоставляет службы PowerPoint для пользователей, работающих с клиентами, отличными от Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f7a21-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="f7a21-109">Вместо этого пользователи подключаются к службе сервера конференций и просматривают презентации PowerPoint так же, как и в Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f7a21-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="f7a21-110">Это также означает, что у этих пользователей будет доступ к более ограниченным возможностям, предоставляемым Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f7a21-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="f7a21-111">Несмотря на то, что для сервера Office Web Apps (Кроме обновления до Lync 2013) не требуется никакой конфигурации клиента, рекомендуется обновить участников Конференции до Internet Explorer 9.</span><span class="sxs-lookup"><span data-stu-id="f7a21-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="f7a21-112">Хотя доступ к конференциям можно получить с помощью Internet Explorer 8, на использование данного браузера накладываются некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="f7a21-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="f7a21-113">Например, пользователи Internet Explorer 8 не смогут свободно изменять размер этапа PowerPoint, вместо этого им придется выбирать один из трех предварительно заданных размеров этапа.</span><span class="sxs-lookup"><span data-stu-id="f7a21-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="f7a21-114">Кроме того, пользователи Internet Explorer 8 не смогут воспроизводить мультимедийные файлы.</span><span class="sxs-lookup"><span data-stu-id="f7a21-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

