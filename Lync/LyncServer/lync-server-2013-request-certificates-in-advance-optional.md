---
title: 'Lync Server 2013: заблаговременный запрос сертификатов (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="09893-102">Заблаговременный запрос сертификатов для Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="09893-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09893-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="09893-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="09893-104">Сертификаты необходимы для всех внутренних серверов, на которых работает Lync Server 2013, включая каждый сервер переднего плана Enterprise Edition, сервер Standard Edition, режиссер, пограничный сервер и изолированный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="09893-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="09893-105">Несмотря на то, что для внутренних серверов рекомендуется использовать внутренний центр сертификации (ЦС) предприятия, вы также можете воспользоваться общедоступным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="09893-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="09893-106">Сведения о требованиях к сертификатам и об использовании общедоступного центра сертификации можно найти в разделе [требования к сертификатам внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="09893-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="09893-107">Lync Server 2013 Setup включает мастер сертификатов, который упрощает задачи запроса, назначения и установки сертификатов во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="09893-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="09893-108">Если вы хотите запросить сертификаты перед установкой серверов (например, для экономии времени на реальном развертывании серверов), можно воспользоваться компьютером, на котором установлены средства администрирования Lync Server 2013, или с помощью запроса сертификата. процедура, определенная в вашей организации, при условии, что сертификаты должны быть экспортированы и содержат все необходимые дополнительные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="09893-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="09893-109">Предварительный запрос сертификатов не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="09893-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="09893-110">Если вы не запрашиваете их заранее, вы должны запросить их в ходе настройки каждого сервера, которому требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="09893-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="09893-111">В этой документации по развертыванию содержатся инструкции по использованию мастера сертификатов для запроса сертификатов в процессе установки, как описано в разделе [Настройка сертификатов для сервера в Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [Настройка сертификатов для режиссера](lync-server-2013-configure-certificates-for-the-director.md)в Lync сервер 2013 и [Установка сервера исправлений в Lync Server 2013 в](lync-server-2013-install-the-files-for-mediation-server.md) разделах этой документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="09893-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="09893-112">Если вы захотите предварительно запросить сертификаты, вы должны изменить процедуры развертывания сертификата в этих разделах так, чтобы они были импортированы и назначены для импорта и назначения сертификатов, а не для их запроса во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="09893-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09893-113">Lync Server 2013 включает поддержку сертификатов SHA-256 для подключений клиентов, работающих под управлением операционных систем Windows Vista,&nbsp;windows Server 2008,&nbsp;Windows&nbsp;Server 2008 R2 и Windows 7, а также Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="09893-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="09893-114">Для поддержки внешнего доступа с помощью SHA-256 внешний сертификат выдается общедоступным центром сертификации с помощью SHA-256.</span><span class="sxs-lookup"><span data-stu-id="09893-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

