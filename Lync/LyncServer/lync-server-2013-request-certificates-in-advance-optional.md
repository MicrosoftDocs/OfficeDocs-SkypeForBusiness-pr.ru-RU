---
title: 'Lync Server 2013: запросить сертификаты заранее (необязательно)'
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
ms.openlocfilehash: d7e671fe61f5d8b9e43593bf99e0ecf0e1e37109
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511966"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="59d30-102">Запрос сертификатов в предварительной (необязательный) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59d30-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59d30-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="59d30-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="59d30-104">Сертификаты необходимы для всех внутренних серверов, на которых работает Lync Server 2013, в том числе для каждого сервера переднего плана Enterprise Edition, сервера Standard Edition, директора, пограничного сервера и изолированного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="59d30-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="59d30-105">Хотя для внутренних серверов рекомендуется внутренний центр сертификации (ЦС) предприятия, можно также использовать общедоступный ЦС.</span><span class="sxs-lookup"><span data-stu-id="59d30-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="59d30-106">Сведения о требованиях к сертификатам и использовании общедоступного ЦС приведены в статье [требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="59d30-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="59d30-107">Lync Server 2013 Setup включает мастер сертификатов, который упрощает задачу запроса, назначения и установки сертификатов во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="59d30-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="59d30-108">Если необходимо запросить сертификаты перед установкой серверов (например, для экономии времени при фактическом развертывании серверов), это можно сделать с помощью компьютера, на котором установлены средства администрирования Lync Server 2013, или с помощью процедуры запроса сертификата, определенной в Организации, при условии, что сертификаты являются экспортируемыми и содержат все обязательные альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="59d30-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="59d30-109">Предварительный запрос сертификатов является необязательным.</span><span class="sxs-lookup"><span data-stu-id="59d30-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="59d30-110">Если вы не запрашиваете их заранее, их необходимо запросить в процессе настройки каждого сервера, для которого требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="59d30-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="59d30-111">В этой документации по развертыванию приводятся инструкции по использованию мастера сертификатов для запроса сертификатов в процессе установки, как описано в разделе [Configure Certificate for Servers in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [Настройка сертификатов для директора в Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)и [Установка файлов для сервера-посредника в разделе Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) этой документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="59d30-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="59d30-112">Если сертификаты запрашиваются заблаговременно, необходимо соответствующим образом изменить процедуры развертывания сертификатов в этих разделах, чтобы вместо запроса сертификатов во время развертывания выполнять из импорт и назначение.</span><span class="sxs-lookup"><span data-stu-id="59d30-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59d30-113">Lync Server 2013 включает поддержку сертификатов SHA/256 для подключений клиентов, работающих под управлением операционных систем Windows Vista, Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 и Windows 7, и Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="59d30-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="59d30-114">Для поддержки внешнего доступа с использованием SHA-256 внешний сертификат выдается общедоступным ЦС с использованием SHA-256.</span><span class="sxs-lookup"><span data-stu-id="59d30-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

