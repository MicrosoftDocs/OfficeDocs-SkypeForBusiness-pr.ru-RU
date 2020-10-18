---
title: 'Lync Server 2013: Настройка сертификатов для обратного прокси-сервера'
description: 'Lync Server 2013: Настройка сертификатов для обратного прокси-сервера.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4b84241775bb3594840b68551048c01ff5faba2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575375"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="190e9-103">Настройка сертификатов для обратного прокси-сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="190e9-103">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="190e9-104">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="190e9-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="190e9-p101">Каждый обратный прокси-сервер требует сертификат веб-сервера для использования службой ожидания вызовов. Сертификат веб-сервера должен быть выдан общедоступным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="190e9-p101">Each reverse proxy server requires a web server certificate for use by the listening service. The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="190e9-107">Сведения о данном и других требованиях к сертификатам приведены [в статье требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="190e9-107">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="190e9-108">Настройка сертификата веб-служб для обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="190e9-108">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="190e9-109">На текущем этапе у вас уже должен быть установлен обратный прокси-сервер, включая настройку сертификата веб-служб.</span><span class="sxs-lookup"><span data-stu-id="190e9-109">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="190e9-110">Если это не было сделано до начала развертывания пограничных серверов, используйте процедуры, описанные в разделе [Настройка обратных прокси-серверов для Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) для создания запроса и установки сертификата веб-служб, а затем создайте каждое правило веб-публикации и настройте его для использования сертификата.</span><span class="sxs-lookup"><span data-stu-id="190e9-110">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

